# android-interview-questions-by-firoz
Here is collection for all interview questions asked in different companies in India for an fresher to experienced android developer. 

### Q: What is Android ?

Android is an open-source, linux-based operating system that is used in mobiles, tablets, televisions and growing range of devices encompassing everything from wearable computing to in-car entertainment. It launched in 2003 and Andy Rubin is the founder of Android. Android is an open source project (led by Google but it doesn't belong to them) called AOSP (Android Open Source Project) which is equipped with rich components that allows developers to create and run apps that can perform both basic and advanced functions.

In other words, Android is a stack of software for mobile devices which includes an operating system, middleware and some key applications. The application executes within its own process and its own instance of Dalvik Virtual Machine. Many instances of Virtual Machines run efficiently by a DVM device. DVM executes Java languages byte code which later transforms into .dex format files. The 'purest' version of Android is often referred to as 'stock Android'. Google acquired Android in 2005. Java language is mainly used to write the android code even though other languages can be used. For software development, Android provides Android SDK (Software development kit). Google only charges manufacturers if they also install the Google apps portion of the OS.

*References:-*

https://www.androidpit.com/what-is-android

https://www.javatpoint.com/android-tutorial

https://www.tutorialspoint.com/android/android_overview.htm

http://heavy.com/tech/2013/06/what-is-android-os-operating-system-info-wiki/

https://recombu.com/mobile/article/what-is-android-and-what-is-an-android-phone_M12615.html#

### Q: What is process in OS ? And what is diff b/w process and thread ?
A process is an instance of a program running in a computer. It is close in meaning to task , a term used in some operating systems. A process is basically a program in execution. The execution of a process must progress in a sequential fashion.
* Threads are used for small tasks, whereas processes are used for more 'heavyweight' tasks
* Threads within the same process share the same address space, whereas different processes do not.
* Threads share the address space of the process that created it; processes have their own address space.
* Threads have direct access to the data segment of its process; processes have their own copy of the data segment of the parent process.
* Threads can directly communicate with other threads of its process; processes must use interprocess communication to communicate with sibling processes.
* Threads have almost no overhead; processes have considerable overhead.
* New threads are easily created; new processes require duplication of the parent process.
* Threads can exercise considerable control over threads of the same process; processes can only exercise control over child processes.
* Changes to the main thread (cancellation, priority change, etc.) may affect the behavior of the other threads of the process; changes to the parent process do not affect child processes.

### Q: What happens when activity rotated ?
Activity is recreated after each rotation by default and onCreate() method of activity called again. You can override this behaviour with *configChanges* attribute of the activity tag in AndroidManifest.

Life Cycle of orientation:-

onPause(); 

onSaveInstanceState(); 

onStop(); 

onDestroy(); 

onCreate(); 

onStart(); 

onResume();

### Q: Explain about GCM implementation?

![Alt text](https://androidexample.com/upload/content/Push_notification_Workflow.png "Optional title")

### Q: Object class and its methods ?
The Object class is the parent class of all the classes in java by default.
* The Object class is beneficial if you want to refer any object whose type you don't know. Notice that parent class reference variable can refer the child class object, know as upcasting.
* Object class is present in java.lang package.
* Object class methods are available to all Java classes.
* There are 12 methods in Object class:

| Method | Description |
| --- | --- |
| public final Class getClass() | returns the Class class object of this object. The Class class can further be used to get the metadata of this class. |
| public int hashCode() | returns the hashcode number for this object. |
| public boolean equals(Object obj) | compares the given object to this object. |
| protected Object clone() throws CloneNotSupportedException | creates and returns the exact copy (clone) of this object. |
| public String toString() | returns the string representation of this object.|
| public final void notify() | wakes up single thread, waiting on this object's monitor.|
| public final void notifyAll() | wakes up all the threads, waiting on this object's monitor.|
| public final void wait(long timeout)throws InterruptedException | causes the current thread to wait for the specified milliseconds, until another thread notifies (invokes notify() or notifyAll() method). |
| public final void wait(long timeout,int nanos)throws InterruptedException | causes the current thread to wait for the specified milliseconds and nanoseconds, until another thread notifies (invokes notify() or notifyAll() method). |
| public final void wait()throws InterruptedException | causes the current thread to wait, until another thread notifies (invokes notify() or notifyAll() method). |
| protected void finalize()throws Throwable. | is invoked by the garbage collector before object is being garbage collected.

*Note :* Whenever we try to print any Object reference, then internally toString() method is called.
 
**hashCode() :** For every object, JVM generates a unique number which is hashcode. It returns distinct integers for distinct objects. A common misconception about this method is that hashCode() method returns the address of object, which is not correct. It convert the internal address of object to an integer by using an algorithm. The hashCode() method is native because in Java it is impossible to find address of an object, so it uses native languages like C/C++ to find address of the object.

**Use of hashCode() method :** Returns a hash value that is used to search object in a collection. JVM(Java Virtual Machine) uses hashcode method while saving objects into hashing related data structures like HashSet, HashMap, Hashtable etc. The main advantage of saving objects based on hash code is that searching becomes easy.

*Note :* Override of hashCode() method needs to be done such that for every object we generate a unique number.
 
**equals(Object obj) :** Compares the given object to “this” object (the object on which the method is called). It gives a generic way to compare objects for equality. It is recommended to override equals(Object obj) method to get our own equality condition on Objects.
 
**getClass() :** Returns the class object of “this” object and used to get actual runtime class of the object. It can also be used to get metadata of this class. The returned Class object is the object that is locked by static synchronized methods of the represented class. As it is final so we don’t override it.
 
**finalize() method :** This method is called just before an object is garbage collected. It is called by the Garbage Collector on an object when garbage collector determines that there are no more references to the object. We should override finalize() method to dispose system resources, perform clean-up activities and minimize memory leaks.
Note : finalize method is called just once on an object even though that object is eligible for garbage collection multiple times.
 
**clone() :** It returns a new object that is exactly the same as this object.
