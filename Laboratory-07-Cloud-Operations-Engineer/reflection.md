# Mission Reflection

Doing this laboratory helped me understand that running an application is not the only thing a cloud operations engineer needs to do. We also need to check if the server is working properly and make sure the application can run without problems.

Checking the host server's resources is important even if the containers seem to be working fine. If the server runs low on RAM or disk space, the application might become slow or stop working. By checking the CPU, memory, and storage, we can notice possible problems before they affect users.

If a user says they cannot log in to a web application, I can use the `docker logs` command to check what is happening inside the container. The logs may show errors or failed requests that can help me understand what went wrong and where to start fixing the problem.

I also learned that logs and metrics have different purposes. Logs show specific events and errors, while metrics show numbers related to the application's performance, such as CPU and memory usage. Both are useful because they help us understand what is happening and whether the application is using too many resources.

For large companies that manage thousands of containers, I think tools like Prometheus and Grafana are very helpful. Prometheus collects performance data, while Grafana presents the information through dashboards. This allows engineers to monitor many containers more easily and notice problems that need attention.

Overall, this activity helped me become more familiar with Linux commands and Docker. I learned how to check system resources, run an Nginx container, send HTTP requests, and look for errors in application logs. I also learned how to monitor CPU and memory usage using `docker stats`. I still have more to learn, but this activity helped me feel more confident using the terminal and understanding how to troubleshoot basic problems.
