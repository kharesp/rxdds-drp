# rxdds-drp
Distributed Reactive Processing with DDS and Rx.
The integration of OMG(Object Management Group)'s Data Distribution Service(DDS) with a reactive programming library like Microsoft's Reactive Extensions(Rx), provides an end-to-end dataflow model where data-distribution is performed by DDS and reactive data processing is done by Rx. A variety of Quality-of-Service(QoS) policies offered by DDS can be used for configuring complex data-flow interactions between distributed nodes while Rx can be used for composing operators in a Functional-Reactive (FRP) style to process data. 

Distributed Reactive Programming(DRP) provides a number of advantages over observer pattern which is traditionally used for implementing reactive applications - applications that must react to incoming data or events, for example User-Interface(UI) applications, Web applications, online analytics, etc. DRP makes the application code more succinct and focussed on application logic, obviating the need to explicitly encode callbacks, callback registries or their management. Furthermore, since DRP provides automatic change propagation and re-evaluation of dependenices on the whole, race-conditions on account of multiple observer callbacks are avoided. 

However, ensuring the proper order of update/change propagation to ensure consistent results is a challenge in the distributed setting due to failures and network latencies. Several reactive languages ensure consistent or glitch-free update propagation in the local setting however very few reactive languages that support distribution also provide glitch-freedom under distribution. 
Moreover, those that do provide glitch-free DRP assume that failures cannot happen, have limited degree of concurrent update propagation, have high co-ordination/synchronization overhead for propagating change or don't offer relaxed consistency guarnatees for applications to better trade-off desired consistency and performance. 

The objective of this project is to explore how the above mentioned limitations can be addressed in our DRP system that integrates Real Time Innovation(RTI)'s implementation of DDS with Microsoft Rx, while leveraging the inbuilt QoS policies that DDS offers. The anticipated milestones for the project are: 

1) Understanding the failure modes of a DRP application and the relevant QoS policies that can be used to redress the same. Then, integrate support for pertinent DDS QoS policies in our existing solution. 

2) Implementing state-of-the-art SID-UP (Source Identifier Update Propagation) algorithm for consistent change propagation in our solution as a starting point; implementing a sample test application and logging assessment metrics like - number of co-ordination messages, degree of parallel updates under different network topologies and resource utilization. 

3) Enhancing existing solution either by adding support for fault-tolerance or support for multiple consistency guarantees, or implementing a new update propagation algorithm that has lower complexity, resource usage and higher degree of concurrent updates. 

A more detailed presentation on the motivation and objectives of this project can be found [a relative link](rxdds-drp.pptx) 


