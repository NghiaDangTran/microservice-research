# What we usually do
Before diving into the topic, let's look at the normal workflow that most of us usually follow in a project. Designing the API, creating the front end, writing code, handling authentication, managing business processes, etc. We do all of these things, but what we may not realize is that this approach falls under what people call a `monolithic` design. In this model, all of your code literally stay in one codebase and runs on a single server or machine.
<p align="center">
  <img src="https://github.com/NghiaDangTran/microservice-research/assets/33323750/0bf5015c-7d44-4cb5-9616-d6ddd161faaa" />
</p>

So, it's normal, and we use it every day, but why consider a new design? What happens if we need to change something quickly? This problem might seem minor with a small codebase, but imagine having a large codebase with multiple functions, and you need to fix one of them right away. You'd have to pull the code version, fix the issue, package (or build) the code, and then publish it again. This process can take time, and until it's complete, the function might not work as expected.


</br>
Just a fun fact: I used to work with React Native, and sometimes updating a critical part would require waiting up to 6 hours just for Google to allow our changes to go public.
</br>

# New type of design
from that painpoint we have design call `Microservice` like the name sugest we will break the function into smaller codebase that run entierly on a container or a server, sounds easy enough right, but it also come with some curse
<p align="center">
  <img src="https://github.com/NghiaDangTran/microservice-research/assets/33323750/338543fe-6ea2-4cb8-a7d4-22f983cf8cf9" />
</p>


# How to Communicate Between Each Service

# How to Split Functions


# How to handle CICD

# How to handle Security

# How to handle Availability

