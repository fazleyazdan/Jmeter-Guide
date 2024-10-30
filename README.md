
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
   - [Interleave Controller](#inter-controller)
   - [ThroughPut Controller](#through-controller)
- [Test Fragment](#test-frag)
- [Parameterization](#parameter)
   - [Internal parameters](#internal-params)
   - [User defined Variables](#user-defined)
   - [Read Params Values for CSV/Excel](#csv-params)
- [Correlation](#correlation)
   - [Regular Expressions](#regexp)




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
* To add: right click thread group --> add--> logic controllers --> simple controller 

![Timer in JMeter](./images/7.%20simple%20&%20module%20controllers/2.%20simple%20controller.png)

<a id="module-controller"></a>

#### Modular controller:
Modular controller is used to call other controllers
* To add: right click thread group --> add--> logic controllers --> modular controller

![Timer in JMeter](./images/7.%20simple%20&%20module%20controllers/6.%20module%20cntrl%20menu.png)

* Here as you can see i have called the simple controller from the module controller

<a id="test-frag"></a>

#### Test Fragment:
Test Fragment is also a container. It is an alternative of Simple Controller.
* To add: right click thread group --> add--> test fragment

![Timer in JMeter](./images/7.%20simple%20&%20module%20controllers/4.%20test%20fragment.png)

![Timer in JMeter](./images/7.%20simple%20&%20module%20controllers/5.%20TestFrag%20menu.png)

<a id="include-controller"></a>

#### Include Controller:  
Include controller is used to call exported requests or scripts.
Same like modular controller but you have to export the request in order to use it.
* To add: right click thread group --> add--> logic controllers --> include controller
* to export the request : right click sampler --> save as test fragment

#### Random Controller:
If we put multiple requests in random controller it will select one request randomly out of all requests.
In the below example we have added 2 request under random controller & it will select one request randomly.
* To add: right click thread group --> add--> logic controllers --> random controller

![Timer in JMeter](./images/8.%20random%20&%20rand%20order%20controller/1.rand%20controller.png)

* Here as you can see, b/w register & login request one is executed randomly.

#### Random Order Controller:
Random Order controller will execute all requests inside it but in random order.
* To add: right click thread group --> add--> logic controllers --> Random Order controller

In the below example we have 3 request added to random order controller. Which is executed randomly.

![Timer in JMeter](./images/8.%20random%20&%20rand%20order%20controller/2.%20rand%20order%20controller.png)

<a id="inter-controller"></a>

#### Interleave Controller:
If there are 2 requests inside the interleave controller. And the loop count is 2 for that thread group.
Then in first loop count the first request will be executed. Now in second round the second request in order, will be executed
And the first will be ignored because it has already executed.

* To add: right click thread group --> add--> logic controllers --> Interleave controller

![Timer in JMeter](./images/8.%20random%20&%20rand%20order%20controller/3.%20interleave%20controller.png)

Here as you can see in the above demo, in random controller there is a chance of request to be executed again,
But in interleave controller the request executed won't be executed again.

<a id="through-controller"></a>

#### Throughput Controller

Throughput controller are used for distributed load test.
Lets say we have 10 user in a thread group. Under the thread group we have 3 samplers. [home, about us, apply now]

![Timer in JMeter](./images/9.%20Throughput%20controllers/1.%20thread%20group.png)

* Now all the 10 users will send requests to all the 3 samplers.
* Now if you want 2 user to send req to the 'home' page, 3 user to 'about-us' page & 5 users to 'apply now' page.
* One solution is to make multiple thread groups, specify the number of users in it and then put specific sampler under that thread group.

![Timer in JMeter](./images/9.%20Throughput%20controllers/2.%20multiple%20thread%20group.png)

* But there is a disadvantage , if the total number of users are changed then we will have to distribute the users again.
Meaning we have to change the number of users per thread group.

* Solution to the above problem is **throughput controller.** Throughput controllers are used for distributing load.

![Timer in JMeter](./images/9.%20Throughput%20controllers/3.%20throughput%20controller.png)

* we have 10 users in thread group
* Here I have created 3 throughput controllers under which I have kept the samplers.
* Now I have selected percent execution for throughput contoller1 meaning (2 requests out of 10)
* Similarly 30 percent for throughput contoller2 meaning (3 requests out of 10)
* And 50 percent for throughput contoller3 meaning (5 requests out of 10)

![Timer in JMeter](./images/9.%20Throughput%20controllers/4.%20aggregate%20report.png)

One of the **advantages** of **throughput controller** is that if the total number of user changed then we don’t have
To change throughput controllers because the users are distributed based on the percentage.

Suppose I change the total number of users to 20. the load will be automatically distributed according to the percentage
We have defined on throughput controller.

![Timer in JMeter](./images/9.%20Throughput%20controllers/5.%20aggregate%20report%202.png)

<a id="parameter"></a>

### Parameterization:

![Timer in JMeter](./images/10.%20parameterization/1.%20parameterization.png)

<a id="internal-params"></a>

#### 1. Jmeter Internal Parameterization:

* When we use parameters which is defined in user variable in Jmeter, we call it internal Parameterization.
* Here I have used this API , which contains parameters/queries. 
https://api.openweathermap.org/data/2.5/weather?q=Islamabad&appid=2896c9038a03da71c1c96f82c778ddb4

* There are 2 queries here ,now to use it as an internal parameter , declare those in user defined variable

<a id="user-defined"></a>

#### User defined variables:

![Timer in JMeter](./images/10.%20parameterization/2.%20add%20user%20defined%20var.png)

* below I have defined variables 

![Timer in JMeter](./images/10.%20parameterization/3.%20menu%20user%20defined.png)

* And then used it in the following request

![Timer in JMeter](./images/10.%20parameterization/4.%20using%20internal%20parameters.png)

![Timer in JMeter](./images/10.%20parameterization/5.%20send%20request.png)

This is called internal parameterization in Jmeter. You can also store URL in a variable.

<a id="csv-params"></a>

#### 2. Read parameter values from CSV/Excel:

![Timer in JMeter](./images/10.%20parameterization/6.%20add%20csv%20for%20external%20parameters.png)

* Then browse the file which contain parameter values

![Timer in JMeter](./images/10.%20parameterization/7.%20menu%20of%20add%20csv%20file%20.png)

* Run your program you will be able to see the results in listener.

<a id="correlation"></a>

### Correlation:

In simple terms correlation is to capture specific value from the response of the request and then use it in another request.

<a id="regexp"></a>

**Regular expressions:**
Regular expressions are the expressions created with the help of meta characters, xpath or tags which are used to fetch 
Some matching values in the text.

![Timer in JMeter](./images/11.%20correlation/1.%20correlation.png)

![Timer in JMeter](./images/11.%20correlation/2.%20w_correlation.png)

![Timer in JMeter](./images/11.%20correlation/3.%20req%20correlation.png)

![Timer in JMeter](./images/11.%20correlation/4.%20how%20to%20use.png)


* **Step 1:** create test plan

* **Step 2:** add request.  Here I am requesting https://testautomationpractice.blogspot.com/

* **Step 3:** now to capture specific response you have to write regular expression for it. There is a web to write regular expression for capturing specific text or value in response. https://testautomationpractice.blogspot.com/
Paste the response there and then write regular expression for the specified response.

![Timer in JMeter](./images/11.%20correlation/8.%20first%20req%20send.png)

* **Step 4:** make a regular expression of the specified response you wants to use.

![Timer in JMeter](./images/11.%20correlation/6.%20create%20regexp.png)

* Here I have wrote regular expression for all the links I have received in response. But I want to use the 2nd link.

* **Step 5:** add post processor (regular expression extractor) to the request

![Timer in JMeter](./images/11.%20correlation/5.%20add%20reg%20express.png)

![Timer in JMeter](./images/11.%20correlation/7.%20regexp%20menu.png)

* In **Name** you can write name of your choice. Which will be used later in the second request.
* In **regular expression** we write the expression we have made.
* In **template** we write the group number. Here we only have one group so we wrote 1. if there were 2 groups then you can write $1$$2$.
* In **Match No**, we write the specified response number that we wanna use. Since we have two links but I want to use the 2nd so I wrote 2.

**Step 6:** now create second request and use the variable as a reference.

![Timer in JMeter](./images/11.%20correlation/9.%20second%20req.png)

* Here notice that I did not wrote anything in server name & just wrote in path. Because **referenceVar** contains the link of the site That we wants to visit. So no need to write anything in server name or IP.

* Now send request and you will be able to see result.

![Timer in JMeter](./images/11.%20correlation/10.%20view%20result.png)

* Here as you can see the second request is successful. And it used the captured link to send request to it.




