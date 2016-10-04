# High availability

A typical role for a software engineer is to ensure that the website of an enterprise is available to users continuously. This is essential for those enterprises that have their business model based on that website, e.g. Amazon, Bol.com, Facebook, etc. Google calls this role "Site Reliability Engineering".

The goal of this assignment is to demonstrate how the infrastructure of a large website works, and to set up similar infrastructure in a virtualized environment.

## Requirements

This assignment is exploratory, and the end result is not defined in detail. That does not mean that it is non-committal, though. You are expected to aim for *high quality code*, a working solution that could be *used in reality*, and a *deep insight* in the system you have set up.

- Read about the subject in technical literature: what tools are used, what techniques, how are large websites structured? Collect what you have read, write down the highlights. In particular, read about monitoring, caching and reverse proxies, load balacing.
- Find a good case that can be used as a demo, e.g. an open source web application (e.g. Drupal, Wordpress, ...).
- Look for a load testing tool that simulates the behaviour of users (e.g. JMeter, [Goofy]()). Define test scenarios.
- Start with reproducing the [lampstack](https://github.com/bertvv/lampstack) setup
- Add monitoring/metrics gathering. List all metrics you need to follow up on and implement these in the chosen monitoring tool.
- Execute the scenario(s) on the current setup, report on the results. Where are the bottlenecks in this setup?
- Depending on the bottlenecks, change the design of your website infrastructure:
    - Put the database backend on a separate server
    - Split up the web servers and add a load balancer
    - Add a cache so not every page request results in server side processing
- All components are monitored, and the most important metrics can be viewed on a dashboard.
- Simulate software updates on this type of infrastructure: remove some nodes from the load balancer, replace them with new, updated nodes and add them again. Repeat this until all nodes are updated. See e.g. the screencast [Zero-downtime Deployments with Ansible](https://sysadmincasts.com/episodes/47-zero-downtime-deployments-with-ansible-part-4-4).
- The complete setup is automated using Ansible. It has to be possible to set up the entire system with no manual intervention

It is important to show your progress regularly. Work iteratively and make sure you have something working as soon as possible (a *Minimum viable Product*). It is perfectly normal that your first solution lacks major parts of the requirements. Discuss milestones with your teacher.

