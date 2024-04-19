
## Outline:
- [About JMeter](#about-jmeter)
- [Elements in JMeter](#jmeter-elements)
*   - [Thread Group](#thread-group)
*   - [Sampler](#samplers)
*   - [Listeners](#listeners)
*   - [Configuration](#config)



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








*
