### ReentrantLock
java中ReentrantLock是可重入锁，需要手动加锁和释放锁，分为公平锁和非公平锁，默认是非公平锁，创建ReentrantLock对象是如果传入的是true就是创建公平锁
java中synchronized是隐式加锁，是非公平锁


### java中的锁的介绍
锁旨在强制实施互斥排他、并发控制策略。

1、锁开销 lock overhead 锁占用内存空间、 cpu初始化和销毁锁、获取和释放锁的时间。程序使用的锁越多，相应的锁开销越大

2、锁竞争 lock contention 一个进程或线程试图获取另一个进程或线程持有的锁，就会发生锁竞争。锁粒度越小，发生锁竞争的可能性就越小

3、死锁问题，A锁锁住M资源，B锁锁住N资源，现在A锁中的M需要N资源，B锁中的N需要M资源就会造成相互等待卡死，就是死锁

### 锁的种类
  独享锁/共享锁
  独享锁是指该锁一次只能被一个线程所持有。 (ReentrantLock、 Synchronized)
  共享锁是指该锁可被多个线程所持有。 (ReadWriteLock)
  
  互斥锁/读写锁

  独享锁/共享锁这是广义上的说法，互斥锁/读写锁就分别对应具体的实现。在Java中如ReentrantLock就是互斥锁(独享锁)， ReadWriteLock就是读写锁(共享锁)。 独   享锁与共享锁也是通过AQS来实现的
  锁升级：读锁到写锁 (不支持)
  锁降级：写锁到读锁 (支持)

  公平锁/非公平锁
  公平锁是指多个线程按照申请锁的顺序来获取锁。
  非公平锁是指多个线程获取锁的顺序并不是按照申请锁的顺序，有可能后申请的线程比先申请的线程优先获取锁。有可能会造成饥饿现象。
  
  可重入锁
  可重入锁又名递归锁，是指同一个线程在外层方法获取锁的时候，在进入内层方法会自动获取
  
  乐观锁/悲观锁
  乐观锁/悲观锁不是指具体类型的锁，而是看待并发的角度。
  悲观锁认为存在很多并发更新操作，采取加锁操作，如果不加锁一定会有问题
  乐观锁认为不存在很多的并发更新操作，不需要加锁。数据库中乐观锁的实现一般采用版本号，Java中可使用CAS实现乐观锁。
  
  关于各种锁介绍详见https://blog.csdn.net/u010648018/article/details/79750608
  
  
  


  
  
  
