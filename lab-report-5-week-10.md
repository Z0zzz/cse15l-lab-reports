# Lab Report 5
## More Debugging and Testing--With Fancier Tools

> In this lab, we use `vimdiff` to find differences between tests.

### Preliminaries
1. I use the command `vimdiff` to quickly compare the results of the two tests. I store the test results in text files, and then we could use `vimdiff` to compare them.
2. linked to the two test files:
- https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/472.md
- https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/577.md



### Discussions

1. Test file 472
- The output of the provided implementation is correct, according to the CommonMark. 
![lab5_ss1](/images/lab5_ss1.png)
and the correct output should be [/url], as is outputted by the provided implementation. 
- Description of error: although my code has correctly detected the link, i.e., it has correctly identified it, but I have an additional condition that tests for whether the 
"link" that we found is actually a link. Code is below
![lab5_ss2](/images/lab5_ss2.png)
Because this particular link, although it satisfies the condition of CommonMark to be a link, I didn't include it because I demand the link to be of certain format, and I would have to either add more conditions to ensure that this particular format is included, or remove this particular condition.

2.  Test file 577
- The output of my implementation is correct, i.e., it shouldn't output anything. That is, this file shouldn't contain any links, as indicated by CommonMark as well as rendered by VScode, since it is enclosed in an image tag, thus it is not a link. 
![lab5_ss3](/images/lab5_ss3.png)
- Description of error: The provided implementation doesn't have condition checking for the particular markdown feature of having a exclamation mark(!) before each image; it only checks for open and close brackets and parathesis, therefore, although this particular line of markdown indicates that it is an image, it is not only to be detected by the implementation, thus the implementation gives the wrong output.
![lab5_ss4](/images/lab5_ss4.png)
An additional condition should be added to this method, after a potential link is identified.