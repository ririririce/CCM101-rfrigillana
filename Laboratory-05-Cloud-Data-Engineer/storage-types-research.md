# Cloud Storage Types Research

There are three common types of cloud storage: Block Storage, File Storage, and Object Storage. Each type stores data in a different way and is useful for different situations.

| Storage Type | Description | Primary Use Case | Cloud Provider Example |
|---|---|---|---|
| **Block Storage** | Stores data in separate blocks. These blocks can be managed individually and are usually used like a regular storage drive. | It is commonly used for virtual machines, databases, and applications that need fast and reliable storage. | **AWS EBS (Elastic Block Store)** |
| **File Storage** | Stores data as files inside folders and directories, similar to how files are organized on a computer. | It is useful when different users or systems need to access and share the same files. | **AWS EFS (Elastic File System)** |
| **Object Storage** | Stores data as individual objects. Each object contains the actual data, information about the data, and a unique identifier. | It is commonly used for large amounts of files such as photos, videos, backups, and other media. | **AWS S3 (Simple Storage Service)** |

### Why Object Storage is Best for User-Uploaded Images

Object Storage is a good choice for the client's photo-sharing application because it is made for storing large amounts of files such as images and videos. It can handle millions of uploaded photos while keeping them organized and easy to access, which makes it suitable for an application that will continue to grow.
