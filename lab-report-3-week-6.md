# Lab Report 3
## Streamline remote accesses

> This lab report introduces methods and utilities for accessing remote serves.


### Streaming ssh configuration
>we want to simplify the ssh log in process. How could we write less code to access a remote server?

1. we use vim to edit a .ssh file, which will be used to simplify our access to remote server.
![vim_ssh_file](images/editing_ssh_file.png)
2. the content of the file should be as the following. After finishing editing, enter `:wq` to save and quit.
![content_ssh_file](images/content_of_ssh_file.png)
3. now we can ssh with fewer characters of code.
![ssh_with_ssh_file](images/ssh_with_ssh_file.png)
4. we could also `scp` with less characters
![scp_with_ssh_file](images/scp_with_ssh_file.png)

## Github Access and keys
>Just like we use keys to log into the remote server, we now use keys to commit and push into GitHub.
1. After we have generated a key pair, we need to tell GitHub of the public key we are using, so it recognizes us when we commit and push.
![github_key](images/github_key.png)
2. The private key is stored locally in the same place as public key, where we could open with a text editor(here I used vim). But we are not showing its content.
![private_key](images/private_key.png)
3. If we do a new keygen on the remote ieng6 server and follow the first step, then we could commit and push from the ieng6 server onto the github.
![push_remote](images/push_remote.png)
4. The result of the push is found [here](https://github.com/Z0zzz/markdown-parser).


## Copy and scp whole directories
> we could scp files, now we are about to scp directories.
1. we copy the whole directory into ieng6 server with the `-r` option
![scp_directory](images/scp_directory.png)
2. we then show that everything is indeed copied over by running the code.
![run_test_on_ieng6](images/run_test_on_ieng6.png)
3. we then make our lives a little easier by combining what was done above into a single command.
![combine_scp_ssh_test](images/combine_scp_ssh_test.png)
