# Big Data

Today, data is forever expanding and it is so valuable to us. Government collect immense amount of data and they use it to process information like our criminal records, election surveys, and so on. Businesses may use the data to analyze revenues and market their products more efficiently. The things you can do with data is endless.

Now that data is so big and expansive, we call it **big data** (not kidding!).

**Well, how do people manage to keep *big data*? Where do we store them?**

We cannot store big data in a disc! Big data is big for a reason, and when I say big this can potentially mean petabytes of data (1 petabyte = 1 million gigabyte). Imagine how many discs or external hard drive we'll need to maintain to store these data! Yikes!

What companies are actually doing in the real-world is keeping data in the **Cloud**. The data is distributed across a cloud network. There are hundreds of thousands of physical servers powered by some of the most powerful computers all around the world that store these data.

By distributing the data to various servers around the world, we get two benefits:

- Faster access of data
- Faster computation time

**Faster access of data** thanks to thousands of servers that are spread out across the globe. As you live close by any single server out there, your access to it is much faster than asking a server of another country half the globe away to process your data.

**Faster computation time** relies on the fact that multiple servers can work together to help process the data you want. When you work on a project, working together usually mean faster completion time, isn't it?

Now that we know how data is stored, let's learn about **Hadoop**, which makes the process of storing and processing data much more easier and faster.

## Hadoop

Essentially, here's a really basic glimpse into how Hadoop works.

Let's say you want to look for image but the image might be in any one of the servers you host your image in. Hadoop has to look for it!

- Hadoop searches for the image by utilizing the **JobTracker**. This helpful person goes out searching for the right server (**DataNode**) that the image is located. Remember that the image (or any file) can be stored in multiple servers for faster access.
- JobTracker successfully found the server(s). It now sends a **Job File** (think of it like a task to accomplish) to the targeted server(s) and process the required task accordingly. Remember that the process can be run in parallel if more than one server is involved.
- When the process has been completed, an **Output File** sends the file back to the JobTracker.
- The JobTracker sends the file back to us. 
- And viola... we're done!

**What's great about Hadoop?**

You can do so many things with it, such as Machine Learning, statistical analysis, and computational data.

**Learning more about Hadoop's basic functionalities?** Take a look at this [YouTube video](https://www.youtube.com/watch?v=FHVuRxJpiwI).