# JMeter :

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

#### Thread Group:
Each **Thread** Represents a **user/ user request**

![Elements in JMeter](./images/2.%20Elements%20in%20JMeter/2.%20Thread%20group.png)

#### Sampler:
Now what kind of **request** a user can Send. So **sampler** represents different **types** of requests Sent By Thread Group.

![Elements in JMeter](./images/2.%20Elements%20in%20JMeter/3.%20Samplers.png)

#### Listeners:

So Listeners will generate **Report** in Graph, table format etc.

![Elements in JMeter](./images/2.%20Elements%20in%20JMeter/4.%20Listeners.png)

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
    
    At 0 seconds: Nobody is running yet.
    At 1 second: You and one friend start running.
    At 2 seconds: Two more friends join the race.
    At 3 seconds: Three more friends start running.
    And so on…

  By the time 10 seconds pass, all 50 friends are running the race. This gradual start helps avoid a big rush at the beginning, just like how in a real system, users might not all start using a website or app at the exact same moment.
  In JMeter, you can set this ramp-up period to simulate how users gradually start using your website or application, helping you test how it performs under increasing levels of activity.
  
* The number of threads and ramp-up period represents **1 loop count**. For e.g. after the completion of requests from the users during the given time a loop is completed. Here we have given **1** loop count, you can give as many loop count here as you want. If you click **infinite** it will go on *forever*.












