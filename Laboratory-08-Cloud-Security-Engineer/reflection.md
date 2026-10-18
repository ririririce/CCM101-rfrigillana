# Mission Reflection

Completing this laboratory activity helped me understand the importance of securing a server and not just making sure that it works properly. I learned that a host-based firewall provides an additional layer of protection by controlling incoming and outgoing network traffic directly on the server. Even if an attacker gets past the network's main firewall, the host-based firewall can still block connections that are not allowed.

Managing open network ports is also important because every unnecessary open port can become a possible entry point for attackers. By allowing only the ports needed by the server, we can reduce its attack surface and make it harder for unauthorized users to access the system. In this activity, I allowed SSH for remote administration and port 8080 for my Nginx web application while keeping the default-deny policy for incoming traffic.

In a real enterprise environment, leaving a database port such as 3306 for MySQL open to the public internet can be dangerous. Attackers could attempt to guess passwords, exploit security weaknesses, or gain unauthorized access to sensitive information. Database access should be restricted to trusted servers and authorized users instead of being exposed to everyone online.

This mission also changed my perspective on how easily a server can be compromised. Before this activity, I focused more on getting applications to run, but I now understand that proper security settings are just as important. Even a simple mistake, such as leaving unnecessary ports open, can create risks for the entire system.

With eight completed missions, I feel that my GitHub portfolio has become more organized and meaningful. Each laboratory activity has helped me build my knowledge of cloud computing, from basic Linux commands and container management to monitoring and server security. I can also use my repository to show the skills I have practiced and the progress I have made throughout the course.
