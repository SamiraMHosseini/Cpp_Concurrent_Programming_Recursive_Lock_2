# Practice-Multithreading
​CPP_Multithreaded_Practice_RecursiveLock ​

Imagine you have a shared resource, like a cake, that two friends, Alice and Bob, want to access. A normal mutex would allow only one of them to access the cake at a time. If Alice locks the mutex, Bob will have to wait until Alice is done before he can access the cake.

Now, let's say that Alice wants to cut the cake into slices, and each slice needs to be covered by plastic wrap before being put back on the cake
and each of those tasks needs to be done in a different stage or function. To wrap each slice, Alice needs to lock the same mutex again, but this time a normal mutex will cause a deadlock, because Alice already locked the mutex and can't lock it again.

To avoid this situation, we can use a recursive mutex. With a recursive mutex, Alice can lock the mutex multiple times, and only needs to unlock it the same nu​​mber of times to actually unlock it. So, in this example, Alice can lock the mutex, cut a slice, wrap it, cut another slice, wrap it, and so on. When she's finished wrapping all the slices, she can unlock the mutex one final time to actually release it, and then Bob can access the cake.

In summary, a recursive mutex is useful when a thread needs to lock the same mutex multiple times, while a normal mutex can only be locked once.
