# Android Interview Preparation 2025
![Minimal Modern Elegant Background Technology Youtube Channel Art png](https://github.com/user-attachments/assets/c0434cfc-4867-447d-bfab-1407ca461ea9)

### Q.) Could you please brief or introduce yourself?
**Ans**. Speak about yourself, including your experience and your specialization.

### Q.) What was your last project?
**Ans**. Explain the domain of your last project, like health care, Banking, E-commerce, or a restaurant, and briefly explain a little bit about that project.

### Q.) Which modules did you do in your previous project?
**Ans**.  Describe your work here and what you have done in your previous project.

### Q.) Which architectural pattern did you follow in your previous project?
**Ans**. MVVM with clean architecture.

### Q.) Could you please explain how MVVM with clean architecture works?
**Ans**. **MVVM** (Model-View-ViewModel) is an architectural pattern that aims to separate the user interface (View) from the business logic (ViewModel) and data (Model). The ViewModel acts as an intermediary between the View and the Model, exposing data and commands that the View can bind to. This separation enables better testability, maintainability, and flexibility.
The project is divided into three layers:
* Data
* Domain
* Presentation
<br />

**Data Layer**
As the name suggests, it contains our data. Network API interfaces, databases, and Repository Implementation reside in this layer.

**Domain Layer**
Our models (entities containing data) and Repository interfaces are included in this layer. At the same time, the business logic of the project is kept in this layer along with the Use cases.

**Presentation Layer**
The presentation layer serves as the interface between the user and the application, handling user input and displaying the corresponding outcomes.

For a deeper and better understanding, please visit the below-provided link: https://medium.com/@ami0275/mvvm-clean-architecture-pattern-in-android-with-use-cases-eff7edc2ef76

### Q.) What is the difference between MVC, MVP, MVVM with clean architecture and MVI?
**Ans**. **MVC** (Model-View-Controller) -> Model manages data and logic, the View displays information, and the controller connects the Model and View and handles the user input.<br />
**MVP** (Model-View-Presenter) -> Model manages data, views display data and sends user commands to the Presenter. At the same time, the Presenter retrieves data from the Model and presents it to the View.<br />
**MVI** (Model-View-Intent) MVI is a reactive architecture that embraces unidirectional data flow, ensuring that the UI remains consistent regardless of the state. Here, the Model represents the state, View reflects the state, and the intent represents user actions that change the state.<br />
**MVVM** (Model-View-ViewModel) Model manages data and view displays the data, while ViewModel holds and contains UI-related data.

### Q.) What is ViewModel, and how does it work internally?
**Ans**. **View Model** is a lifecycle-aware class, designed to store and manage UI-related data. When a view model is created, it is stored inside the activity or fragment manager. This means that your UI doesn’t have to fetch data again when configuration changes, such as when rotating the screen. It has a ViewModelStore, which stores the instance of ViewModel, and it is retained when the rotation occurs. It returns the same ViewModel instance in the new activity instance as the old destroyed activity.
For a deep understanding of internal work, please visit the mentioned link:  https://medium.com/@KaushalVasava/viewmodels-internal-working-in-android-a-full-guide-757afaf6510

### Q.) What are Android Architecture components?
**Ans**. Android architecture components are a collection of libraries that help you design robust, testable, and maintainable apps. Android Architecture Components are a part of Android Jetpack.
All the Android Architecture Components are as follows:
* **Data Binding**: It helps in declaratively binding UI elements to our layout to the data sources of our app.
* **Lifecycles**: It manages the activity and fragment lifecycles of our app, survives configuration changes, avoids memory leaks and easily loads data into our UI.
* **LiveData**: It notifies views of any database changes. Use LiveData to build data objects that notify views when the underlying database changes.
* **Navigation**: It handles everything needed for in-app navigation in Android applications.
* **Paging**: It helps in gradually loading information on demand from our data source.
* **Room**: It is an SQLite object mapping library. Use it to avoid boilerplate code and easily convert SQLite table data to Java objects. Room provides compile-time checks of SQLite statements and can return RxJava, Flowable and LiveData observables.
* **ViewModel**: It manages UI-related data in a lifecycle-conscious way. It stores UI-related data that isn't destroyed on app rotations.
* **WorkManager**: It manages every background job in Android with the circumstances we choose.

### Q.) What is the lifecycle of Activity and Fragment?
**Ans**: 
**Activity LifeCycle Methods**:<br />
OnCreate   OnStart   OnResume   OnPause   OnStop   OnRestart  OnDestroye <br />
**Fragment LifeCycle Methods**:<br />
OnAttach  OnCreate  OnActivityCreated  OnViewCreated  OnStart OnResume  OnPause  OnStop OnDestroyeView OnDestroye onDetech

When combining the fragment with activity, we try to understand the life cycle.
**Step 1**: Launch the activity
MainActivity OnCreate
MainFragment OnAttach
MainFragment OnCreate
MainFragment OnCreateView
MainFragment OnActivityCreated
MainFragment OnStart
MainActivity OnStart
MainActivity OnResume
MainFragment OnResume
<br />
**Step 2**: Press the back button
MainFragment OnPause
MainActivity OnPause
MainFragment OnStop
MainActivity OnStop
MainFragment OnDestroyView
MainFragment OnDestroy
MainFragment OnDetech
MainActivity OnDestroy

### Q.) How do we share data between fragments?
**Ans**: Using Shared ViewModel and Using nav arguments from Nav graph.

### Q.) What are the SOLID principles, and how do they explain them?
**Ans**. **SOLID** is an acronym for five design principles that help create maintainable, scalable, and robust code.<br />
**S: Single Responsibilities**: (A module should have one, and only one reason to change, like a Singleton class.)<br />
**O: Open(To extension)/ Closed(To Modification)**: (This means you can add new things to a class without changing its original code. So, instead of changing the class itself, you can write new code that uses the existing class to add new features. Doing this makes the code easier to maintain and reuse).<br />
**L: Liskov Substitution**: It means that the child type should be able to replace the parent without changing the behavior of the program.<br />
**I: Interface Segregation**: The class that implements the interface shouldn’t be forced to use the methods it does not need.<br />
**D: Dependency Inversion**:

### Q.) What is LiveData and Mutable Live Data? 
**Ans**. **LiveData**: It is used to observe the data on activity. It is a part of the observer pattern. We can assign value only once, but we can assign or modify value at runtime.<br />
**Mutable LiveData**: It is also used to observe the data on activity. It is also a part of the observer pattern. We assign value multiple times. We can assign or modify the value at run time.

### Q.) What are the differences between Parcelable and Serializable?
**Ans**. **Parcelable** is an Android-specific interface, and **Serializable** is a Java-specific interface.<br /> 
**Parcelable** is faster than **Serializable**.<br /> 
**Parcelable** consumes less memory than **Serializable**.<br />
```
Implementations:
@Parcelize
data class Developer(val name: String, val age: Int) : Parcelable

data class Developer(val name: String, val age: Int) : Serializable
```
### Q.) What are the differences between CompileSdkVersion and TargetSdkVersion?
**Ans** * The **compileSdkVersion** is the version of the API the app is compiled against. This means you can use Android API features included in that version of the API (as well as all previous versions, obviously). If you try and use API 16 features but set compileSdkVersion to 15, you will get a compilation error. If you set compileSdkVersion to 16, you can still run the app on an API 15 device as long as your app's execution paths do not attempt to invoke any APIs specific to API 16.<br />
* The **targetSdkVersion** has nothing to do with how your app is compiled or what APIs you can utilize. The targetSdkVersion is supposed to indicate that you have tested your app on (presumably up to and including) the version you specify. This is more like a certification or sign-off that you are giving the Android OS as a hint to how it should handle your app in terms of OS features.

## Flow API : 
### Q.) What is Flow, and how does it work?
### Q.) What is the use of StateFlow?
### Q.) What is the difference between StateFlow and Live data? 
### Q.) How to execute multiple tasks parallelly and collect results at the same time?  
### Q.) How to handle quick search functionality using flow and how it works?
### Q.) How to do exception handling using flow?


## Security related:  
### Q.) Which library do you use for network api calling?
**Ans**. **Retrofit**: Its simplicity, flexibility, and strong integration with Kotlin’s coroutine support. Retrofit simplifies the process of making HTTP requests and processing responses.
### Q.) What are the interceptors, and how do they work?
**Ans**. An **interceptor** in OkHttp is a powerful mechanism that sits between the application and the network. It intercepts and modifies HTTP requests and responses, enabling developers to perform various tasks like logging, authentication, caching, and more.
```
For example, Authentication Interceptor:
val authInterceptor = Interceptor { chain ->
    val originalRequest = chain.request()
    val authenticatedRequest = originalRequest.newBuilder()
        .header("Authorization", "<your_access_token>")
        .build()
    chain.proceed(authenticatedRequest)
}
val client = OkHttpClient.Builder()
    .addInterceptor(authInterceptor)
    .build()
```
### Q.) How do you handle security concerns during network calls?
**Ans**. **Authentication**: Credential Manager and Biometric authentication.<br />
**TLS** (Transport Layer Security) / **SSL** (Secure Sockets Layer): It is a cryptographic protocol that Encrypted Communication Over the Network.
 ```
 val request = Request.Builder()
        .url("https://yourserver.com/api")
        .build()
```
OkHttp automatically negotiates the TLS handshake when connecting to the server via HTTPS. If the server doesn’t support TLS, the request will fail, ensuring that the communication is secure.<br />

**Certificate Pinning / SSL Pinning**: It is a security technique that helps prevent man-in-the-middle (MITM) attacks by ensuring that the app communicates only with trusted servers using a specific SSL certificate.<br />

**Network Security Configuration file**: The Network Security Configuration feature uses an XML file where you specify the settings for your app. You must include an entry in your app's manifest to point to this file.<br />
```
<?xml version="1.0" encoding="utf-8"?>
<network-security-config>
    <domain-config>
        <domain includeSubdomains="true">abc.com</domain>
        <trust-anchors>
            <certificates src="@raw/abc”/>
        </trust-anchors>
    </domain-config>
</network-security-config>
```
### Q.) What is SSL pinning, and how does it work?
**Ans**. **SSL pinning** is a security technique that helps prevent man-in-the-middle (MITM) attacks by ensuring that the app communicates only with trusted servers using a specific SSL certificate.
```
val certificatePinner = CertificatePinner.Builder()
        .add("yourserver.com", "sha256/AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA=")
        .build()
val client = OkHttpClient.Builder()
        .certificatePinner(certificatePinner)
        .build()
```
### Q.) How did you handle authentication and authorization in your last project?
**Ans**. **Authentication**: Verifying the identity of a user attempting to access the app, such as Password-based authentication, biometrics (fingerprint, facial recognition), social logins (Google, Facebook), token-based authentication (OAuth) and multi-factor authentication (MFA).<br />
**Authorization**: Determining whether a user has the necessary permissions to perform specific actions within the app, such as the Android permissions framework.

### Q.) How do you store authentication tokens securely?
**Ans**. **Android Keystore**: Android Keystore provides a secure storage option for cryptographic keys, including keys used for encrypting tokens. You can encrypt the token and store it in the Keystore for enhanced security.<br />
**Cryptography**: It is a technique of securing information and communications. It can Encrypt and Decrypt information using Encoding and Decoding algorithms, respectively.

### Q.) How do I refresh the token if it has expired?
**Ans**. We can refresh the auth token inside the auth intercepter with the expired time and current time. 
Please check with the mentioned link for deeper and better understanding: https://medium.com/@manuchekhrdev/access-token-expiration-refresh-token-retrofit-interceptor-coroutines-c3c75069de86 

## Dependency Injection:
### Q.) What is dependency injection, and why do we need to use it?
**Ans**. **Dependency injection** is a design pattern and technique used to manage and provide dependencies to various components of an Android application. It makes your code more flexible and reusable.
Dependency Injection Advantages:
> Reduced Boilerplate Code
> Improved Testability
> Easier Maintenance
> Better Modularity and Scalability

### Q.) What is a hilt, and how does it work?
**Ans**. **Hilt** is an official dependency injection library for Android that is built on top of Dagger 2 and provides a simplified and streamlined approach to dependency injection in Android apps.
**Key features** associated with Hilt:
* Integration with Android Jetpack components like activities, fragments, services, and view models.
* Predefined injection components such as @AndroidEntryPoint and @HiltViewModel can handle the injection logic for Android classes
* Scoping of dependencies (@Singleton, @ActivityScoped, etc.) helps define the injected objects' lifespan and visibility.

### Q.) What is the scope of the hilt, and how many types?

## Database related:
### Q.) What is the best way to store local data securely?
**Ans**. **Room**: The Room persistence library provides an abstraction layer over SQLite to allow for more robust database access.

### Q.) What is the room database, and how does it work?
**Ans**. **Room Database** is now highly recommended for local storage in Android development and is one of the Android Jetpack’s architecture components. It is an upgraded version of the SQ-Lite database.

**Advantages** of the Room database over SQ-Lite DB:
1. Reduce boilerplate code.
2. Compile-time check to reduce the run-time errors and null pointer exceptions.
3. Faster execution compared to SQ-Lite DB because of using predefined annotations.
4. It is easy to migrate and upgrade the versions of the database.

It has 3 main components:
1. **Database** — Abstract class or Singleton
2. **Entity** (table) — Data class
3. **DAO** (Database Access Object) — Interface class; it makes queries on the Entity using API.

```Room Library works with Observable frameworks like Rxjava & Live data.```

**Annotations** are: 
```
@Entity 
@Dao
@Database, and many more.
```
# Kotlin Specific Questions

### Q.) Why should we use Kotlin, and how does it work exactly?
**Ans** **Kotlin** is an object-oriented and functional programming language. It is an improved version of Java to reduce the risk of run-time errors with the use of compile-time checks and better performance solutions than Java. We have a few use cases that prove that Kotlin is a better option than Java for Android Development.
1. **Null Safety**: Kotlin doesn’t allow the creation of null objects due to compile-time checks. With the help of compile-time checks, we can reduce the risk of Null Pointer exception.
    > A few ways to handle nullability are Safe Call operator ( ?. ), Elvish Operator ( ?: ), and Assertion Operator ( !! )
2. **Extension Functions**: Adding additional new functionality in existing class without making any change in code or without inheriting from a class. For example, ImageView.loadImage(url: String), String.formattedText(input : String)
3. **Coroutines Support**: Kotlin provides a solution to handle the asynchronous operations and concurrency simply and efficiently. It is a lightweight thread that allows you to write asynchronous code sequentially, making it easier to manage background tasks like network requests and database operations. For example, CoroutineScope(Dispatchers.IO).launch { }
4. **Data Class**: This class is used to hold the data without creating getter and setter methods. Use cases of Data class is request and response class for network api call. For example, data class User(var name: String, var id: Int)
5. **Functional Programming**: It means to handle the computation of mathematical functions.
    1. **High Order Functions**:  This type of function accepts function as an input parameter and as a return type. 
    2. **Lamda Expression**: It is an anonymous function without any specific names. We can use this as a functional literal to execute mathematical expressions.
6. **Smart Casts**: Automatically casts a variable to its target type after checking conditions.
7. **Interoperability with Java**: Kotlin can seamlessly interact with Java code, enabling easy migration from Java to Kotlin.

### Q.) What is the difference between const, val and var in Kotlin?
**Ans** **val** (value) is used for read-only variables, which means they cannot be reassigned after initialization (like final in Java).<br />
	**var** is used for mutable variables, which can be reassigned any number of times.  <br />
**Real-Time Example**:
	val x = 10   // Read-only, cannot be reassigned
	x = 20       // Error: Val cannot be reassigned

	var y = 15   // Mutable, can be reassigned
	y = 30       // Okay, no problem

**const**, It represents an immutable, final variable in nature like val, i.e. read-only properties. The difference here is that const is used for variables that are known at **compile time**. It means no values must be assigned at runtime to a const variable.
For example, const val AUTHOR_NAME = “Satnam"
In Java, final static String AUTHOR_NAME = “Satnam";

**Properties**:  1. Must be at the top level or a member of an object or a companion object.
2. Start from a primitive data type.

### Q.) What are the parameters and arguments?
**Ans** **Parameters**, defined variable names with their data types. <br />
For example, fun add(num1: Int, num2: Int) = num1 + num2
// num1 and num2 are parameters
// By default num1 and num2 are val variables

**Arguments**, passing value for those parameters while calling the functions.<br />
For example, add(5,7) // 5 and 7 are arguments

### Q.) What is String, and how does it store values? 
**Ans**. **String** is the final class, and it is used to create objects to store literal values in their memory areas.<br />
**Heap Area**<br />
**SCP/SLP**( String Constant Pool/ String Literal Pool)

For e.g. String s1 = new String(“Test”);<br />
         Here, it will create 2 objects. <br />
	     It will store value. 1 object in Heap Memory and 1 object will be stored in SCP.<br />
String s2 = “Test1”;<br />
Here, it will create only one object, which will be stored as a value in SCP. It will not create a new object if the same value is already available. It will reuse that value.

### Q.) What are the Array and List?
**Ans**. **Array**, It is an object that stores multiple values with the same data type and with a fixed size.<br />
For example, var arr = arrayOf(“One”,”Two”,”Three”)<br />
**List**, It is an object that stores multiple values with different data types and with a dynamic size.<br />
For example, var list = listOf(“One”,”Two”,”Three”)<br />

### Q.) What are the differences between Ranges of for loop(.. and until)?
**Ans**. **1..5**, It means that it will check the value from 1 to 5 like 1,2,3,4,5. <br />
For example, for(i in 1..5){ println(i) }<br />
**1 until 5**, It means that it will check the value from 1 to 4 like 1,2,3,4. <br />
For example, for(i in 1..5){ println(i) }

### Q.) What is a data class in Kotlin, and why should we use it?
**Ans**. A **data class** is a kotlin class that is primarily used to hold the data. Kotlin automatically provides methods like toString(), equals(), hashCode(), and copy() for data classes.<br />
**Use cases**:<br/>
* **Reducing boilerplate**: You don't need to manually define getters, setters, toString(), or equals() methods.<br />
* **Copying objects**: You can easily copy an object with modifications.<br />
	Real-Time Example:
	data class User(val name: String, val age: Int)

	val user1 = User("Satnam", 25)
	val user2 = user1.copy(age = 26)  // Create a copy with age updated

	println(user1)   // Output: User(name=Satnam, age=25)
	println(user2)   // Output: User(name=Satnam, age=26)

### Q.) What are extension functions in Kotlin, and how do they work internally?
**Ans**. **Extension functions** allow you to add new functionality to existing classes without modifying their source code. It is a powerful feature in Kotlin, especially useful when dealing with third-party libraries.<br/>
**Real-Time Example**: <br/>
Imagine you want to add a isEmailValid() function to the String class:<br/>
> fun String.isEmailValid(): Boolean {<br/>
>   return this.contains("@") && this.contains(".")<br/>
> }

> val email = "test@example.com" <br/>
> println(email.isEmailValid())  // Output: true

Here, we added the isEmailValid() function to the String class without modifying its code.

### How does it work internally?
When we call extension function on an object, the compiler passes the object as the first argument to the function.
For example, 
> public static final void loadImage(ImageView imageView, String url) {<br/>
>      Glide.with(imageView).load(url).into(imageView);<br/>
>   }

**A final note**:<br/>
* Extension functions are defined outside the class they extend.<br/>
* They can access the public members of the extended class.<br/>
* They cannot access the class's private or protected members.<br/>
* They do not modify the actual class but appear to add new methods.
