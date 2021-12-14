这辆车多了一个人使用：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly439s1xfj30f20az40u.jpg)

当传进来的对象赋值给当前对象的属性，代表传入的对象多了一个人使用，所以我们应该先为这个传入的对象发送一条retain消息，再赋值；当当前对象销毁的时候，代表属性指向的对象少一个人使用，就应该在dealloc中release
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly43jfs8aj30bj0b50w7.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly43qq5edj30f20azdjm.jpg)

宝马车未被销毁，发生内存泄露：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly43xxjs3j30eh0csgod.jpg)
当我们将传入的Car对象赋值给_car属性的时候，有两重意思：一个是_car属性原本指向的对象少一个人使用，另一个是新传入的对象多一个人使用；所以我们应该先将_car属性原本指向的对象release，再将传入的新对象retain

![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4453h1pj30b304pwg3.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly44cdm33j30eh0csgqq.jpg)


出现僵尸对象错误的原因：在于新旧对象是同一个对象
解决的方案：当发现新旧对象是同一个对象的时候，什么都不用做；只有当新旧对象不是同一个对象的时候，才release旧的，retain新的
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly44k48nfj30en0b4wi1.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly44qyyydj306x0680tu.jpg)


```objectivec
#import<Foundation/Foundation.h>
#import "Person.h"

int main(int argc,const char * argv[]){
    
    Person *p1=[Person new];

    Car *bmw=[Car new];
    bmw.speed=100;
    p1.car=bmw;

    [bmw release];

    bmw.speed=200;
    p1.car=bmw;

    [p1 release];

    return 0;
}
```

```objectivec
#import<Foundation/Foundation.h>

@interface Car : NSObject{
    
    int _speed;
}

- (void)setSpeed:(int)speed;
- (int)speed;

- (void)run;

@end
```

```objectivec
#import "Car.h"

@implementation Car

- (void)dealloc{

    NSLog(@"速度为%d的车子销毁了.",_speed);
    [super dealloc];
}

- (void)setSpeed:(int)speed{

    _speed=speed;
}

- (int)speed{

    return _speed;
}

- (void)run{

    NSLog(@"速度为%d的车正在行驶",_speed);
}

@end
```

```objectivec
#import<Foundation/Foundation.h>
#import "Car.h"

@interface Person : NSObject{

    Car *_car;
}

- (void)setCar:(Car *)car;
- (Car *)car;

- (void)drive;

@end
```

```objectivec
#import "Person.h"

@implementation Person

- (void)dealloc{

    NSLog(@"人死了");
    [_car release];
    [super dealloc];
}

- (void)setCar:(Car *)car{

    //说明新旧对象不是同一个对象
    if(_car != car){

        [_car release];   //才去release旧的
        _car = [car retain];    //retain新的
  }
}

- (Car *)car{

    return _car;
}

- (void)drive{

    NSLog(@"走啊，去拉萨");
    [_car run];
}

@end
```

特别注意：我们内存管理的范围是OC对象，所以，只有属性的类型是OC对象的时候，这个属性的setter方法才要像上面那样写【对象类型就是类或协议所声明的指针类型，例如:NSString *string ,其中，NSString是一个类，NSString *是它指针类型或叫对象类型。】