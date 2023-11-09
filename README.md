# SparkGitMicrochallenge


## INFO:
This is a Spark! microchallenge for getting familiar with git!  
This is called a repository. Repositories are used to store files and to store several different commits, or versions of your code. During development, you often want to commit your code to show your process from the ground up. You also might want to update working code into a new version, while still keeping the previous version.  
In our repository, we have a few files; our **README.md** file, which is the file you are reading right now, our **Sort.java** file, which is a java file that sorts a given array, and our **Message.java** file, which we will use to print things out and test our code. You are going to be using GitHub commands in a codespace to edit these files and create new files. 

#### We will NOT be editing any files directly; instead, we will be using git commands in the terminal (exception: step 8)
#### YOU MUST COMMIT AFTER EVERY STEP THAT TELLS YOU TO COMMIT! Only commit the file you changed in each step. If you do not follow this direction, you may not be able to complete the challenge, and you may have to restart

### Commands you should know for this microchallenge (<> represent values that should be changed; DON'T include the <> characters in the changed value):  
>   ☆ **touch** -- touch \<file\> -- if \<file\> doesn't exist, it creates the file; if it does exist, it will update the timestamps of the file.  
>   ☆ **append** -- echo \<thing to append\> >> \<file\> -- appends \<thing to append\> to \<file\>; you can use single or double quotes.  
>   ☆ **create new branch** -- git branch \<branch name\> -- creates a new branch called \<branch name\>  
>   ☆ **switch to a different branch** -- git checkout \<branch name\> -- switches into the branch called \<branch name\>  
>   ☆ **_committing_**; use all these commands sequentially, together ->  
>   |  ☆ **_add files for commit_** -- git add \<file\> \<file2\> \<file\> <...> -- adds file(s) to be committed  
>   |  ☆ **_commit message_** -- git commit -m "\<message here\>" -- adds a message to your commit  
>   |  ☆ **_push the commit_** -- git push -- NO arguments, pushes the files staged.  
>   ☆ **commit history** -- git log -- view the commit history, including commit messages and authors.  
>   ☆ **delete a commit**; be very careful when doing this. the following commands deletes a specific commit ->  
>   |  ☆ git rebase -i \<commit hash before the one you want to remove\>  
>   |  ☆ git push origin \<branch name\> --force
  
## Step 0: IMPORT the repository  
Instead of cloning, we're going to import our repository. To do this, first, click the green **Code** button, and copy the HTTPS key. Then, click the image of your profile in the top right -> Your repositories -> New -> Import a repository. Copy your URL key into the box, and name the repository; you can give it the same name or create a new one. Then, click begin import. This is the process you would use if you had a local repository.  
Now, in this repository, you can open a codespace (also under the green code button).  
  
## Step 1: Create a "vars.java" file.  
Let's create a new file using our codespace. In the terminal, use the "touch" BASH command to create vars.java. Then, you can append the following to that file ->  
`public class vars { public static void main(String[] args) { } public static String getName() {String name = "__name__"; return name; } public static String welcome() { return "Welcome to the Spark! Git Microchallenge!"; } }`  
Remember that Java doesn't care about whitespace or indents, which is why we can append this all as one line. Also, notice that there are double quotes in the above code, so you will have to use single quotes to append.   
  
  
## Step 2: Update our name variable in vars.java  
Use Bash command `sed -i -e 's/__name__/[your name here]/g' vars.java`  
**Commit!**  

## Step 3: Append some code to Message.java  
Append the following to your Message.java file:
`public static void tester(int[] test) { String testString = ""; for (int i = 0; i < test.length; i++) { testString += test[i]; } }`  
**Commit!**  

## Step 4: Create a branch  
Create a new branch called temp, and move into it. Use the command `git push --set-upstream origin temp` to ensure proper commits from here on.  

## Step 5: Create a "decode.java" file  
Create the file and append this code:
`public class decode {public static void main(String[] args) {}public static String decoder(int[] arr) {String result = ""; for (int i = 0; i < arr.length; i++) {result += String.valueOf( (char)arr[i] );}return result;}}`  
**Commit!**  
  
## Step 6: Create a file order.java  
Create the code and append this code:
`public class order { public static void main(String[] args) { } public static String asciiOrder(String phrase) { int[] arr = new int[phrase.length()];for (int i = 0; i < phrase.length(); i++) { arr[i] = (int) phrase.charAt(i); } 
Sort.selectionSort(arr); return decode.decoder(arr);} } `  
**Commit!**

## Step 7: Merge with main  
Let's merge the branch we're in, temp, in main. Make sure you move into the main branch first!
**Commit!**

## Step 8: Whoops! We have to remove one of our commits
We actually **didn't** have to append any code to Message.java in step 4, so we want to remove this commit. Since we have been committing regularly, we can just remove that commit and revert to the version of Message.java before step 4. Make sure to follow the exact syntax above! In the file that opens when you run the command to delete a commit, delete the line that corresponds to the commit you’re trying to delete, save by clicking the three lines in the top left -> file -> save, and then close that file by hitting the ‘x’ on its tab. _(hint: if your log isn't long enough, press enter a few times; type q to exit the log)_  

## Step 9: Run our Message.java file!  
You can run directly in the codespace (not by using a command, but by clicking the pages icon (Explorer) on the left side, clicking the Message.java file, clicking the triangle (run and debug), and then green 'run and debug' button. It may prompt you to install an extension; install the first one it shows you, hit run again, and say yes to any prompts)
The output should appear in the terminal. You should get a link in return. Copy this into your browser and see where it takes you!
You should also see the String "Spark! Git Microchallenge" re-arranged in Ascii order!

