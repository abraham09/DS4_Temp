## Lesson 4 Homework: Command Line Chipotle

#### Submitting Your Homework

* Create a Markdown file that includes your answers **and** the code you used to arrive at those answers.
* Add this Markdown file to a GitHub repo that you'll use for all of your coursework.
* Submit a link to your repo using the homework submission form listed just below the course schedule on the class repo on the main README.md page. [(submission form)](https://docs.google.com/forms/d/e/1FAIpQLScH_m8Le4w0sqsvm5uNOTd08p4KDTW8WgnWVP1kFf4CCBi2Ow/viewform)

#### Command Line Tasks

1. Look at the head and the tail of **chipotle.tsv** in the **data** subdirectory of this repo. Think for a minute about how the data is structured. What do you think each column means? What do you think each row means? Tell me! (If you're unsure, look at more of the file contents.)
 > <code>
 cd ds-sea-4
 cd data
 head chipotle.tsv
 tail chipotle.tsv
 </code>

 - Columns showing order, quantity, item, description and price, most likely all of the orders that they have received/carry at their store

2. How many orders do there appear to be?
> <code>
 tail chipotle.tsv
 </code>
 - 1834 since the first line is the header
3. How many lines are in this file?
>  <code>
  wc -l chipotle.tsv
 </code>
 - 4,623
4. Which burrito is more popular, steak or chicken?
 > <code>
   grep -i "chicken burrito" chipotle.tsv | wc -l  
   grep -i "steak burrito" chipotle.tsv | wc -l 
   </code>
   - **553 chicken**
   - 368 steak
5. Do chicken burritos more often have black beans or pinto beans?
 > <code>
   grep -i "chicken burrito.* pinto" chipotle.tsv | wc -l 
   grep -i "chicken burrito.* black" chipotle.tsv | wc -l 
   </code>
   - 69 chicken burritos with pinto
   - **212 chicken burritos with black**

6. Make a list of all of the CSV or TSV files in the [our class repo] (https://github.com/ga-students/DS-SEA-3). repo (using a single command). You will be working on your local repo on your laptop.  Think about how wildcard characters can help you with this task.
 > <code>
   find . -name *.??v
   </code>

7. Count the approximate number of occurrences of the word "dictionary" (regardless of case) across all files of [our class repo] (https://github.com/ga-students/DS-SEA-3).
 > <code>
   grep -ir "dictionary" . | wc -l 
   </code>
   - **95**

8. **Optional:** Use the the command line to discover something "interesting" about the Chipotle data. Try using the commands from the "advanced" section!

  > <code>
    uniq chipotle.tsv | wc -l
   </code>
   - **4589 unique entries (when left as is an unsorted)**
