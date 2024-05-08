
## Outline:
- [About JMeter](#about-jmeter)
- [Elements in JMeter](#jmeter-elements)
   - [Thread Group](#thread-group)
   - [Sampler](#samplers)
   - [Listeners](#listeners)
   - [Configuration](#config)
- [Timers in JMeter](#jmeter-timer)
   - [Constant Timer](#const-timer)
   - [Uniform Random Timer](#uniform-timer)
     - [Uniform Random Timer Explained](#uniform-explained)
   - [Other Timers in JMeter](#other-timer)
- [Controllers in JMeter](#jmeter-controller)
   - [Loop Controller](#control-loop)
   - [Recording Controller](#jmeter-record)
   - [Simple Controller](#simple-controller)
   - [Modular Controller](#module-controller)
   - [Include Controller](#include-controller)
- [Test Fragment](#test-frag)




<a id="about-jmeter"></a>

### What is JMeter :

![JMeter](./images/1.%20JMeter/1.%20Jmeter.png)

### Advantages of JMeter :

![Advantages of JMeter](./images/1.%20JMeter/2.%20Advantages.png)

### Platform Independent: 
* Meaning it can run on Windows, Mac etc

### Visualize test results:
* Meaning we can generate different kinds of reports

### How Does JMeter Works:

![Working of JMeter](./images/1.%20JMeter/3.%20Jmeter_working.png)

<a id="jmeter-elements"></a>

### Elements in JMeter:

![Elements in JMeter](./images/2.%20Elements%20in%20JMeter/1.%20elements%20in%20jmeter.png)

Here **Thread Group** is an element.
**Samplers** etc … are also elements.
Then we have Sub Elements Like **Request**, **publisher** etc.

### Main Elements in JMeter:
* **Thread Group**
* **Samplers**
* **Listeners**
* **Configuration**

<a id="thread-group"></a>

#### Thread Group:
Each **Thread** Represents a **user/ user request**

![Elements in JMeter](./images/2.%20Elements%20in%20JMeter/2.%20Thread%20group.png)

<a id="sampler"></a>

#### Sampler:
Now what kind of **request** a user can Send. So **sampler** represents different **types** of requests Sent By Thread Group.

![Elements in JMeter](./images/2.%20Elements%20in%20JMeter/3.%20Samplers.png)

<a id="listener"></a>

#### Listeners:

So Listeners will generate **Report** in Graph, table format etc.

![Elements in JMeter](./images/2.%20Elements%20in%20JMeter/4.%20Listeners.png)

<a id="config"></a>

#### Configuration element:
In configuration we define the common **variable** used in **Samplers**.

![Elements in JMeter](./images/2.%20Elements%20in%20JMeter/5.%20Config%20Elements.png)

### Creating First Test In JMeter:

![Elements in JMeter](./images/3.%20Create%20test%20plan/1.%20steps%20to%20create%20JMeter%20test.png)

1. Open JMeter:

2. Test Plan is Auto created when you open JMeter. you can change the name of the test plan in **Name** section.

![Elements in JMeter](./images/3.%20Create%20test%20plan/open_JMeter.png)

All elements will come/created under Test plan.

3. Create a Thread Group **(Users)**:

* --> Right Click on the test plan --> Click Add --> Thread(users) --> Thread Group.

![Elements in JMeter](./images/3.%20Create%20test%20plan/2.%20Add%20thread.png)

![Elements in JMeter](./images/3.%20Create%20test%20plan/3.%20Thread_menu.png)

* Here in **Name** section specify the name of the thread Group. I have given *Thread Group*.
* in **Comments** you can write *explanation* or details or leave it *empty*.
* In **Number** of threads we specify the Number of User Requests.
* In **Ramp-up period** we specify the *frequency*, after how much time a user should send request. 
  For e.g. we have 3 users, so a user send a request now other users will send request after some time but not all at once.
* **Ramp-up explained:**
  Imagine you're running a race with your friends. If everyone starts running at the same time, it might be chaotic and crowded. But if you start the race with a "ramp-up period," it's like gradually letting everyone start running over a bit of time instead of all at once.
  
  Here's a simple example:
  
  Let's say you have 50 friends and you want to start a race. You decide on a ramp-up period of 10 seconds.
    
   * At 0 seconds: Nobody is running yet.
   * At 1 second: You and one friend start running.
   * At 2 seconds: Two more friends join the race.
   * At 3 seconds: Three more friends start running.
   * And so on…

  By the time 10 seconds pass, all 50 friends are running the race. This gradual start helps avoid a big rush at the beginning, just like how in a real system, users might not all start using a website or app at the exact same moment.
  In JMeter, you can set this ramp-up period to simulate how users gradually start using your website or application, helping you test how it performs under increasing levels of activity.
  
* The number of threads and ramp-up period represents **1 loop count**. For e.g. after the completion of requests from the users during the given time a loop is completed. Here we have given **1** loop count, you can give as many loop count here as you want. If you click **infinite** it will go on *forever*.

4. Add a **Sampler**:

Here we will add HTTP request type. (There are many Request Types)

![Elements in JMeter](./images/3.%20Create%20test%20plan/4.%20add%20sampler.png)

![Elements in JMeter](./images/3.%20Create%20test%20plan/5.%20sampler%20menu.png)

*   In **Name** section we give name to our request.
*   In **comment** section we add comments.
*   We can leave the **Protocol** Section empty as it is already selected in this case it 'http'.
*   **Server Name or IP:** we write the IP .For e.g. I am using website to send request. *https://jmeter.apache.org/index.html*. 
*   Keep in mind that we will only write this *'jmeter.apache.org'* in server or IP.
*   If there is a route in this case it is 'index.html' we will write it in Path section. Remember if there is no route. '/'    represents home page of web.
*   **HTTP Request:** represent the type of request call. Here we are using 'GET'.
*   After this click on **'Add'** button below to add sampler.

5. Add **Listeners:**

    *   Here we will add **3 types of listeners** to generate report. (They are popular)

![Elements in JMeter](./images/3.%20Create%20test%20plan/6.%20add%20listener.png)

![Elements in JMeter](./images/3.%20Create%20test%20plan/7.%20listener%20menu.png)

6. After that click save the test plan. Click **save** icon

7. Then run it. By clicking the **Start Icon**

8. After that switch to the **Result Tree** or **Summary Report** or **View result tree in table** to view the result of the requests.they will appear below the **Requests**.

#### View Result Tree **Menu**:

![Elements in JMeter](./images/3.%20Create%20test%20plan/8.%20view%20report.png)

    • Here as you can see all of my requests are successful.
    • You can clear the result by clicking on the 'clear all' icon.

#### View Report in Table **Menu**

![Elements in JMeter](./images/3.%20Create%20test%20plan/9.%20view%20report%20in%20table.png)

* Here 'Latency' represents the time it took for user request to hit the server.

* 'Connection time' represents the time a user took in establishing the connection with the server.

<a id="jmeter-timer"></a>

### Timers in JMeter :

![Timer in JMeter](./images/4.%20Timers%20in%20JMeter/1.%20timers.png)

![Timer in JMeter](./images/4.%20Timers%20in%20JMeter/2.%20types%20of%20timers.png)

Most of the times we will use Constant & Uniform Random Timer. They are the Most popular.

<a id="const-timer"></a>

1. **Constant Timer**

* You can add Timers on thread level as well as sampler level.
* If you have created timers on thread level then it will be applied to all the requests inside the thread.

to create **Constant Timer** on thread level :

![Timer in JMeter](./images/4.%20Timers%20in%20JMeter/3.%20add%20const%20timer.png)

![Timer in JMeter](./images/4.%20Timers%20in%20JMeter/4.%20const%20timer%20menu.png)

Here I have given 3 seconds for each request at thread level. So it will take min 9 seconds (more or less) to complete those requests. It can take more than this time as well.

![Timer in JMeter](./images/4.%20Timers%20in%20JMeter/5.%20listner%20after%20adding%20timer.png)

* If you create timer at both the *thread* & *sampler* level then both the thread level & sampler level timer
Will be applied to that specific sampler(request). 

#### Adding constant timer for a specific request:

Here I have created timer at sampler level for the first request.

Note: for the request both timer will be applied, the thread timer as well as self timer of the request.

![Timer in JMeter](./images/4.%20Timers%20in%20JMeter/6.%20adding%20timer%202.png)

Since we have defined timer for the first sampler/request, it will start after 6 seconds. Because both the timers are triggered for it. (6+3+3 = 12s) more or less

![Timer in JMeter](./images/4.%20Timers%20in%20JMeter/7.%20listner%20after%20adding%20timer%202.png)

**NOTE:** We can also 'Disable' Requests and timer by right clicking on these elements & click disable option.

<a id="uniform-timer"></a>

2. **Uniform Random Timer**

In Uniform Random timer we will send a request at random time.

**Example:** we sent a request after 3 seconds. Another request will send after 5 seconds.
Meaning the request sending time will not be same for all requests, it will be random.

* Formula for Uniform Random based on which delay time for requests are calculated:

![Timer in JMeter](./images/4.%20Timers%20in%20JMeter/8.%20uniform%20random%20timer.png)

<a id="uniform-explained"></a>

In JMeter, the Uniform Random Timer is a timer that adds a random delay before each sampler (HTTP request, JDBC request, etc.) executes. 
This random delay helps simulate more realistic user behavior by introducing variability in the timing of requests. Now, let's break down the two parameters you mentioned:

      Constant Delay Offset: This is the minimum amount of time, in milliseconds, that the timer will wait before each sampler executes. It's called "constant" because this delay remains the same for each request. For example, if you set the Constant Delay Offset to 500 milliseconds, each sampler will wait at least 500 milliseconds before executing.
      
      Random Delay Maximum: This parameter specifies the maximum additional time, in milliseconds, that the timer may wait before executing a sampler. It adds randomness to the delay. For instance, if you set the Random Delay Maximum to 1000 milliseconds, the timer will randomly choose a delay between 0 milliseconds and 1000 milliseconds to add to the constant delay offset.

Here's an example to illustrate how these parameters work together:
  • Constant Delay Offset: 5000 milliseconds
  • Random Delay Maximum: 1000 milliseconds

When you use this timer, each sampler will wait at least 5000 milliseconds (the constant delay offset), plus an additional random delay between 0 and 1000 milliseconds (the random delay maximum), before executing.
So, if the timer randomly selects 700 milliseconds as the additional delay for a particular sampler, that sampler will wait a total of 500 milliseconds (constant) + 700 milliseconds (random) = 1200 milliseconds before executing.

In summary, the Constant Delay Offset provides a fixed minimum delay, while the Random Delay Maximum adds variability by introducing a random delay on top of the minimum delay. Together, they help create a more realistic load on your system under test.

* **Adding uniform random timer on thread level:**

![Timer in JMeter](./images/4.%20Timers%20in%20JMeter/10.%20adding%20uniform%20random%20timer.png)

![Timer in JMeter](./images/4.%20Timers%20in%20JMeter/11.uniform%20random%20timer%20menu.png)

<a id="other-timer"></a>

3. Other Timers :

![Timer in JMeter](./images/4.%20Timers%20in%20JMeter/9.%20other%20timers.png)

<a id="jmeter-controller"></a>

## Controllers in JMeter:

![Controllers in JMeter](./images/5.%20controller%20in%20JMeter/1.%20controller%20in%20jmeter.png)

<a id="control-loop"></a>

1. **Loop Controller**

![Controllers in JMeter](./images/5.%20controller%20in%20JMeter/2.%20loop%20controller.png)

On the thread level when we specify the loop count, it is **applicable** to all the samplers/requests.
Now to send a request a **specific** number of times we use loop controllers.

* **Adding loop controller :**

![Controllers in JMeter](./images/5.%20controller%20in%20JMeter/3.%20adding%20loop%20controller.png)

* Here I have added loop controller to **'wpct home'** request , that it should execute **2 times.**
* Add **'controller'** on the thread level then you can add **specific samplers** to it.

![Controllers in JMeter](./images/5.%20controller%20in%20JMeter/4.%20loop%20controller%20menu.png)

* **NOTE:** if you add loop on the thread level as well as individual loops, then both the loops will be applied to the request.

![Controllers in JMeter](./images/5.%20controller%20in%20JMeter/5.%20adding%20request%20to%20controller.png)

* you can add the request to the controller by drag & drop.

* Now run the program & note that 'wpct home' is executed two times.

![Controllers in JMeter](./images/5.%20controller%20in%20JMeter/6.%20result%20after%20adding%20the%20controller.png)

* You can also add *Listeners* to the individual requests. Then only the result of that request will be shown in the listeners.

![Controllers in JMeter](./images/5.%20controller%20in%20JMeter/7.%20listener%20with%20specific%20request.png)

<a id="jmeter-record"></a>

### Recording in Jmeter:

![Recording in JMeter](./images/6.%20recording%20controller/1.%20recording%20in%20JMeter.png)

* What are recorder used for in Jmeter?
* So recorder records the transactions between the client & server, which consists of request & response.

So first of all

1. **Add NonTestElement - http recording**

![Timer in JMeter](./images/6.%20recording%20controller/2.%20adding%20non%20testEle.png)

![Timer in JMeter](./images/6.%20recording%20controller/3.%20menu%20of%20nonTestEle.png)

Here in **Port** , write the **port number** on which your browser will be running

In **transaction name** write anything which is descriptive

Write your desired value in **create new transaction after request.**

2. Set proxy on browser:

In search menu type **internet options**. Click on it and then go to **Connection** --> click **LAN Setting**

![Timer in JMeter](./images/6.%20recording%20controller/4.%20browser%20proxy.png)

* Give the same port number as in Jmeter. Which was '8888' in my case
* Since we are running Jmeter on localhost. So address will be the same.

3. Add recording controllers

![Timer in JMeter](./images/6.%20recording%20controller/5.%20adding%20recording%20cntrl.png)

* Add two recording controllers one for **Registration** & other for **login**. as we will do record for these two.

![Timer in JMeter](./images/6.%20recording%20controller/6.%20menu%20of%20rec%20control.png)

* Now as we have added the controllers, we have to start them.
* Go to Http test script. Expand target controllers.

![Timer in JMeter](./images/6.%20recording%20controller/7.%20select%20controller.png)

* Here as you can see , now click on the 'registration' or 'login'.
* Start the recording by clicking on the 'start' icon, & go to the web page. The transactions will be recorded under the   Registration recording controller.
* Also stop recording after login or registration.

![Timer in JMeter](./images/6.%20recording%20controller/8.%20start%20recording%20cntrlr.png)

* The request recorded will be shown below the respective **recording controller**

![Timer in JMeter](./images/6.%20recording%20controller/9.%20registration%20list.png)

* Add a listener on a thread level, to see which of the requests are failing and passing

![Timer in JMeter](./images/6.%20recording%20controller/99.%20result%20tree%20after%20adding%20listener.png)

#### Using these things collectively

![Timer in JMeter](./images/7.%20simple%20&%20module%20controllers/1.%20Controllers.png)

<a id="simple-controller"></a>

#### Simple Controllers:

Simple controller is like a container which can have one or multiple requests.
So basically the simple controller itself won't perform any actions. It is just a container & used to group the requests.
* **NOTE:** if there are samplers or listener etc.. inside the simple controller then it will be executed.

![Timer in JMeter](./images/7.%20simple%20&%20module%20controllers/2.%20simple%20controller.png)



















