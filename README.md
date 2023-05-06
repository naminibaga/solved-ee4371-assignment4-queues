Download Link: https://assignmentchef.com/product/solved-ee4371-assignment4-queues
<br>



The problem is to simulate a network node. Packets arrive randomly at the switch, and are sent out every ∆<em>t </em>seconds. If too many packets arrive, they are queued. A maximum of <em>N </em>packets can be queued. To model the arrival of packets at the node, you can use the following function nextTime() which gives the next time a packet arrives for a Poisson process.

#include &lt;math.h&gt; #include &lt;stdlib.h&gt; int nextTime(float rateParameter)

{ return (int)(-logf(1.0f – (float) random() / (RAND_MAX + 1)) / ratePar }

The argument <em>rateParameter </em>is 1<em>/</em>∆<em>t </em>and a parameter of your simulation. If the queue grows too large, packets are dropped.

A packet is an instance of a structure as follows:

typedef struct{

int id; // packet id int t0; // arrival time of packet int priority; // higher means more important char contents[80]; // contents of packet

} PACKET;

We will not use priority here, but this can be a standard definition for a packet for later assignments. When a packet is to be added, you need to first allocate it via

PACKET *p;

p = (PACKET *)malloc(sizeof(PACKET));

and then add it to the queue. Note that queue is a circular array of pointers, each pointing to a packet or to NULL (if that queue element is not allocated

<ol>

 <li>Write a program that will take λ= 1<em>/</em>∆<em>t</em>, <em>N </em>and µ (the rate at which packets are forwarded by the node) and simulate the queue. λ and µ are real while <em>N </em>is integer. The program must collect a history of the time spent in the queue and the percentage of packets dropped.</li>

 <li>Vary the three parameters as follows and generate histograms for each case and enter the missing databelow:</li>

</ol>

1

<table width="453">

 <tbody>

  <tr>

   <td width="32"><em>N</em></td>

   <td width="44">λ</td>

   <td width="36">µ</td>

   <td width="84">Avg Delay</td>

   <td width="137">% dropped packets</td>

   <td width="119">Time per packet</td>

  </tr>

  <tr>

   <td width="32">5</td>

   <td width="44">0<em>.</em>45</td>

   <td width="36">0<em>.</em>5</td>

   <td width="84">?</td>

   <td width="137">?</td>

   <td width="119">?</td>

  </tr>

  <tr>

   <td width="32">10</td>

   <td width="44">0<em>.</em>45</td>

   <td width="36">0<em>.</em>5</td>

   <td width="84">?</td>

   <td width="137">?</td>

   <td width="119">?</td>

  </tr>

  <tr>

   <td width="32">20</td>

   <td width="44">0<em>.</em>45</td>

   <td width="36">0<em>.</em>5</td>

   <td width="84">?</td>

   <td width="137">?</td>

   <td width="119">?</td>

  </tr>

  <tr>

   <td width="32">5</td>

   <td width="44">0<em>.</em>4</td>

   <td width="36">0<em>.</em>5</td>

   <td width="84">?</td>

   <td width="137">?</td>

   <td width="119">?</td>

  </tr>

  <tr>

   <td width="32">5</td>

   <td width="44">0<em>.</em>3</td>

   <td width="36">0<em>.</em>5</td>

   <td width="84">?</td>

   <td width="137">?</td>

   <td width="119">?</td>

  </tr>

 </tbody>

</table>

and understand the way <em>N </em>and λ interact.

<ol start="3">

 <li>Is the time complexity to manage the queue per packet equal to O(1) or something else? Assume that all CPU and memory operations are the same cost (which they are not).</li>

</ol>