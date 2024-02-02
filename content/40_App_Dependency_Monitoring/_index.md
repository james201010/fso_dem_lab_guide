+++
title = "App Dependency Monitoring"
chapter = false
weight = 4
+++

**Re-factoring Bridge-To-Posibili-Tea's application has taken Antonio on a journey of using third party services that allows his team to focus on the features that really impact the business bottom line while some of the needed functionalities are fulfilled by services provided by other companies.**

![image](/images/antonio2.0.png)

---

## Current situation

Although using third-party services releases the team from having to architect, design, code, test, deploy and maintain supporting code, it does not exempt them from owning the performance of those services being used.

This situation adds a degree of complexity to the operation of the business as functionalities needed by the business are not controlled internally, leaving the operations team with SLAs as the sole source of quality control.

From Bridge-to-Posibili-Tea's perspective their visibility ends the moment the request for services to third parties leave their infrastructure (wheather it is in the cloud or on premises) so, if there are problems they are unable to triage those as they will not be able to tell if the issue is happening with the data in transit (while the request is being transported to the third party or the result is being delivered back to them) or at rest (when the request reaches the third party service and is processed).

![Broken Dependency](/images/BrokenDependency.png)


## Cisco's FSO - Dependency Monitoring

Cisco's FSO - Dependency Monitoring solution includes ThousandEyes which allows you to gain deep visibility into the performance of data in transit through a network of agents spread all around the globe along with enterprise agents installed in the customer's infrastructure which provide insights to what kind of issues your data is finding while moving through the internet.

These insights enable customers to very easily, quickly and intuitively understand if performance issues observed with interactions with third-party services are due to problems in the public/private internet or if they are happening at rest (when the third parties are actually processing the requests).

This triage ability provides customers with undisputable data that will allow them to timely react and document their response according to the circumstances.

![DependencyInsights - ThoushandEyes](/images/DependencyInsights_ThousandEyes.png)


## Why should Antonio care?

If Antonio is blind in regards to why a third-party service is presenting a performance degradation then there is little leverage he has while raising the issue to them.  Being able to articulate any claim with solid data enables Antonio to address third-party-services' issues in a asertive way which leads to MTTR reduction.

Giving the increasingly dependency modern applications have with the ecosystem of services provided by others it is very important to be able to have a verifiable understanding of the circumstances under which a third-party service degrades such that the appropriate corrective actions can be taken in a timely manner.  

<br>

## Next <span style="color: #143c76;"><i class='fas fa-cog fa-spin fa-sm'></i></span>&nbsp;

We'll see how AppDynamics and ThousandEyes provides you with the visibility to quickly identify issues with third party services to get to root cause.

<br>

