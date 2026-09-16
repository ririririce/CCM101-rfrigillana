# My Mission Reflection

This laboratory activity helped me understand the difference between using a Virtual Machine and using a Docker container. One thing I noticed is that a Docker container can be started much faster than a VM because it does not need to install and boot a complete operating system. Instead, it shares the host operating system's kernel, which makes it lighter and faster to set up. When I deployed Nginx, I only needed a few Docker commands before I could access the web server.

I also learned why port mapping is important when running a web server inside a container. The `-p 8080:80` option connects port 8080 on the host to port 80 inside the container, where Nginx is running. Because of this, I was able to use `curl http://localhost:8080` and see the Nginx welcome page. Before doing this activity, I was not very familiar with how the host and container ports were connected.

Another thing I learned was what happens when using `docker rm`. It removes the container from Docker, and data stored only inside that container can be lost if it was not saved somewhere outside the container. This made me realize that containers are meant to be easy to create, stop, remove, and replace.

I think containerization can also make collaboration between developers and IT operations teams easier. Developers can package an application and its required files into a container, while IT teams can run that same container in different environments. This can help make deployments more consistent and reduce some setup problems.

Lastly, my GitHub portfolio is slowly becoming more complete. With every laboratory activity, I am adding new topics, commands, screenshots, and reflections. This activity helped me add Docker and containerization to my portfolio while also giving me actual experience using Docker in an Ubuntu environment.
