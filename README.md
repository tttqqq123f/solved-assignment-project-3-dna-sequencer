Download Link: https://assignmentchef.com/product/solved-assignment-project-3-dna-sequencer
<br>
Project 3 – DNA Sequencer

Assignment<strong>: </strong>Project 3 – DNA Sequencer

1.  Overview

In this project you will:

<ul>

 <li>Implement a linked-list data structure,</li>

 <li>Use dynamic memory allocation to create new objects,</li>

 <li>Practice using C++ class syntax,</li>

 <li>Practice dynamically allocated arrays,</li>

 <li>Practice object-oriented thinking.</li>

</ul>

2.  Background

Deoxyribonucleic acid (DNA) is a molecule that carries the genetic instructions used in the growth, development, functioning and reproduction of all known living organisms. Most DNA molecules consist of two strands coiled around each other to form a double helix. The two DNA strands are termed polynucleotides since they are composed of simpler monomer units called nucleotides. The nucleotides for DNA are made up of four bases – adenine (A), guanine (G), cytosine (C), and thymine (T).

DNA sequencing is the process of determining the precise order of nucleotides within a DNA molecule. The four nucleotides (G, C, A, T) are paired. This means that if one strand of the DNA has a G, the other strand will have a C. If one strand has an A, the other strand will have a T (and vice-versa). If you have just one of the strands, you have the leading strand. If you have both strands, each pair of nucleotides is called a base pair. Base pairs will always be (A+T, T+A, G+C, or C+G).

The genetic code is the set of rules by which information encoded within genetic material (DNA or mRNA sequences) is translated into proteins by living cells. The code defines how sequences of nucleotide triplets (trinucleotides), called codons, specify which amino acid will be added next during protein synthesis. With some exceptions, a three-nucleotide codon in a nucleic acid sequence specifies a single amino acid.

In simple terms, this means that we can look at three nucleotides (G, C, A, T) and identify the amino acid that it is. For example, the trinucleotide “CAA” equates to glutamine and “AAA” equates to lysine.

Note: In biology, you may have learned about mRNA, and its function in the translation to an amino acid, however, for this project, we will not be dealing with the mRNA translation step (including using uracil instead of thymine).

3.  Assignment Description

Your assignment is to build an application that can read a file of nucleotides into a linked list.

<ol>

 <li>The file contains a sequence of nucleotides (G, C, A, T).</li>

 <li>The file will always contain a multiple of 3 (due to that they are trinucleotides).</li>

 <li>The file needs to be imported into a user made linked list.</li>

 <li>The file is loaded via command line argument (included in the provided <strong>makefile</strong> and <strong>cpp</strong>).</li>

 <li>No static arrays or vectors are allowed in this project although dynamically allocated vectors are allowed.</li>

 <li>All user inputs will be assumed to be the correct data type. For example, if you ask the user for an integer, they will provide an integer.</li>

 <li>Regardless of the sample output below, all user input must be validated. If you ask for a number between 1 and 5 with the user entering an 8, the user should be re-prompted.</li>

 <li>Have a main menu that asks the user if they want to:

  <ol>

   <li>What would you like to do?:

    <ol>

     <li>Display DNA (Leading Strand)</li>

     <li>Display DNA (Base Pairs)</li>

    </ol></li>

  </ol></li>

</ol>

<ul>

 <li>Inventory Basic Amino Acids</li>

</ul>

<ol>

 <li>Sequence Entire DNA Strand</li>

 <li>Exit

  <ol>

   <li>Upon exit, nothing is saved</li>

  </ol></li>

</ol>

4.  Requirements:

Initially, you will have to use the following files <strong>DNA.h, Sequencer.h, makefile, driver.cpp, Translate_to_DNA.cpp,</strong> and a variety of test input for the project. You can copy the files from Prof. Dixon’s folder at:

<strong>/afs/umbc.edu/users/j/d/jdixon/pub/cs202/proj3</strong>

To copy it into your project folder, just navigate to your project 3 folder in your home folder and use the command:

<strong>cp /afs/umbc.edu/users/j/d/jdixon/pub/cs202/proj3/*.* .</strong>

<strong>cp /afs/umbc.edu/users/j/d/jdixon/pub/cs202/proj3/makefile .</strong>

Notice the trailing period is required (it says copy it into this folder) and you need a second command to copy the makefile (*.* does not copy the makefile).

The <strong>Translate_to_DNA.cpp</strong> is a single function that belongs in DNA.cpp.

<ul>

 <li>The project must be completed in C++. You may not use any libraries or data structures that we have not learned in class. Libraries we have learned include <strong>&lt;iostream&gt;, &lt;fstream&gt;, &lt;iomanip&gt;, &lt;vector&gt;, &lt;cstdlib&gt;, &lt;time.h&gt;,</strong> <strong>&lt;cmath&gt;</strong> and <strong>&lt;string&gt;</strong>. You should only use <strong>namespace std</strong>.</li>

 <li>You must use the function prototypes as outlined in the <strong>h and Sequencer.h</strong> header file. Do not edit the header files.</li>

 <li>There are four test files available. They are proj3_numSize.csv. For example, <strong>csv</strong> has 60 nucleotides. <strong>proj3_15000.csv</strong> has 15,000 nucleotides. We should be able to test a file of any size (within reason). We provided test files with 9, 60, 3000, and 15000 nucleotides.</li>

 <li>You need to write the functions for the class (<strong>cpp</strong>) based on the header file (<strong>DNA.h</strong>). The nucleotides (i.e. Nodes) for the linked list that you are implementing are structs that hold two pieces of information – a char and a pointer to the next node. Do not use the STL for this project.

  <ul>

   <li><strong>DNA()</strong> – The constructor creates a new empty linked list. <strong>m_head</strong> and <strong>m_tail</strong> are always NULL and <strong>m_size</strong> is zero.</li>

   <li><strong>~DNA() – </strong>The destructor de-allocates any dynamically allocated memory. (May call clear)</li>

   <li><strong>Clear() –</strong> Clears the linked list.</li>

   <li><strong>InsertEnd() –</strong> Always inserts new nucleotides at the end of the linked list.</li>

   <li><strong>Display() –</strong> Takes in a variable to know how many strands you want to display. 1 shows just the nucleotides that were loaded. 2 shows the nucleotides and their complements (G-C), (C-G), (T-A), or (T-A).</li>

   <li><strong>IsEmpty() –</strong> Returns if the linked list is empty.</li>

   <li><strong>SizeOf() –</strong> Populates m_size of sequencer with how many nucleotides were loaded.</li>

   <li><strong>NumAmino() –</strong> Takes in the name and trinucleotide codon. Counts the number of instances of that trinucleotide codon in just the provided strand. For example, it could take Tryptophan and TGG or Phenylalanine and TTT. It then iterates over the structure to count how many instances of those amino acids exist in the DNA. Additionally, if we had the sequence T-T-T-T-G-G, we would have exactly 2 codons (TTT) and (TGG). The same if we had a sequence that was 15,000 nucleotides long. We would have exactly 5,000 trinucleotide codons. We never count overlapping codons. Run <strong>numAmino</strong> on at least Tryptophan (TGG) and Phenylalanine (TTT).</li>

   <li><strong>Sequence() –</strong> Iterates over entire structure and converts trinucleotides to amino acids for all nucleotides in the file. Stores the amino acid name in a dynamic array. Displays amino acid list.</li>

   <li><strong>Translate() –</strong> Converts a trinucleotide string to an amino acid name. It is available for download in my folder above and is named: <strong>cpp</strong>. Provided below.</li>

  </ul></li>

</ul>

<table>

 <tbody>

  <tr>

   <td width="624"><strong>string DNA::Translate(const string trinucleotide){</strong><strong>  if((trinucleotide==”ATT”)||(trinucleotide==”ATC”)||</strong><strong>      (trinucleotide==”ATA”))</strong><strong>    return (“Isoleucine”);</strong><strong>  else if((trinucleotide==”CTT”)||(trinucleotide==”CTC”)||</strong><strong>      (trinucleotide==”CTA”)||(trinucleotide==”CTG”)||</strong><strong>      (trinucleotide==”TTA”)||(trinucleotide==”TTG”))</strong><strong>    return (“Leucine”);</strong><strong>  else if((trinucleotide==”GTT”)||(trinucleotide==”GTC”)||</strong><strong>     (trinucleotide==”GTA”)||(trinucleotide==”GTG”))</strong><strong>    return (“Valine”);</strong><strong>  else if((trinucleotide==”TTT”)||(trinucleotide==”TTC”))</strong><strong>    return (“Phenylalanine”);</strong><strong>  else if((trinucleotide==”ATG”))</strong><strong>    return (“Methionine”);</strong><strong>  else if((trinucleotide==”TGT”)||(trinucleotide==”TGC”))</strong><strong>    return (“Cysteine”);</strong><strong>  else if((trinucleotide==”GCT”)||(trinucleotide==”GCC”)||</strong><strong>     (trinucleotide==”GCA”)||(trinucleotide==”GCG”))</strong><strong>    return (“Alanine”);</strong><strong>  else if((trinucleotide==”GGT”)||(trinucleotide==”GGC”)||</strong><strong>     (trinucleotide==”GGA”)||(trinucleotide==”GGG”))</strong><strong>    return (“Glycine”);</strong><strong>  else if((trinucleotide==”CCT”)||(trinucleotide==”CCC”)||</strong><strong>     (trinucleotide==”CCA”)||(trinucleotide==”CCG”))</strong><strong>    return (“Proline”);</strong><strong>  else if((trinucleotide==”ACT”)||(trinucleotide==”ACC”)||</strong><strong>     (trinucleotide==”ACA”)||(trinucleotide==”ACG”))</strong><strong>    return (“Threonine”);</strong><strong>  else if((trinucleotide==”TCT”)||(trinucleotide==”TCC”)||</strong><strong>     (trinucleotide==”TCA”)||(trinucleotide==”TCG”)||</strong><strong>     (trinucleotide==”AGT”)||(trinucleotide==”AGC”))</strong><strong>    return (“Serine”);</strong><strong>  else if((trinucleotide==”TAT”)||(trinucleotide==”TAC”))</strong><strong>    return (“Tyrosine”);</strong><strong>  else if((trinucleotide==”TGG”))</strong><strong>    return (“Tryptophan”);</strong><strong>  else if((trinucleotide==”CAA”)||(trinucleotide==”CAG”))</strong><strong>    return (“Glutamine”);</strong><strong>  else if((trinucleotide==”AAT”)||(trinucleotide==”AAC”))</strong><strong>    return (“Asparagine”);</strong><strong>  else if((trinucleotide==”CAT”)||(trinucleotide==”CAC”))</strong><strong>    return (“Histidine”);</strong><strong>  else if((trinucleotide==”GAA”)||(trinucleotide==”GAG”))</strong><strong>    return (“Glutamic acid”);</strong><strong>  else if((trinucleotide==”GAT”)||(trinucleotide==”GAC”))</strong><strong>    return (“Aspartic acid”);</strong><strong>  else if((trinucleotide==”AAA”)||(trinucleotide==”AAG”))</strong><strong>    return (“Lysine”);</strong><strong>  else if((trinucleotide==”CGT”)||(trinucleotide==”CGC”)||</strong><strong>      (trinucleotide==”CGA”)||(trinucleotide==”CGG”)||</strong><strong>      (trinucleotide==”AGA”)||(trinucleotide==”AGG”))</strong><strong>    return (“Arginine”);</strong><strong>  else if((trinucleotide==”TAA”)||(trinucleotide==”TAG”)||</strong><strong>      (trinucleotide==”TGA”))</strong><strong>    return (“Stop”);</strong><strong>  else</strong><strong>    cout &lt;&lt; “returning unknown” &lt;&lt; endl;</strong><strong>  return (“Unknown”);</strong><strong>}</strong></td>

  </tr>

 </tbody>

</table>

<ul>

 <li>You need to code up the various functions that are called in the <strong>cpp</strong> file that are prototyped in <strong>Sequencer.h</strong>.

  <ul>

   <li><strong>Sequencer()</strong> – The constructor builds the DNA (linked list), reads the file, and calls <strong>mainMenu</strong>.</li>

   <li><strong>~Sequencer() </strong>– The destructor de-allocates any dynamically allocated memory.</li>

   <li><strong>ReadFile()</strong>– The <strong>ReadFile</strong> function loads a file of nucleotides into the DNA (linked list). The file itself is passed to the <strong>ReadFile</strong> function from the command line (in driver.cpp which is provided). Also, calls <strong>SizeOf</strong> to populate <strong>m_size</strong>.</li>

   <li><strong>MainMenu()</strong> – Calls the various functions in the DNA (linked list).

    <ul>

     <li>Choices (1 and 2) – calls the DNA function <strong>Display</strong>.</li>

     <li>Choice 3 – calls the DNA function <strong>NumAmino</strong>.</li>

     <li>Choice 4 – calls the DNA function <strong>Sequence</strong>.</li>

     <li>Choice 5 – Exits.</li>

    </ul></li>

  </ul></li>

</ul>

5.  Sample Input and Output

5.1.            Sample Run

A normal run of the compiled code would look like this with user input highlighted in blue:

<table>

 <tbody>

  <tr>

   <td width="624">m-bash-4.1$ make run1./proj3 proj3_9.csvNew Sequencer loadedWhat would you like to do?:1. Display Sequencer (Leading Strand)2. Display Sequencer (Base Pairs)3. Inventory Basic Amino Acids4. Sequence Entire DNA Strand5. Exit1Base Pairs:AAGTGGCTAEND9 nucleotides listed.3 trinucleotides listed.What would you like to do?:1. Display Sequencer (Leading Strand)2. Display Sequencer (Base Pairs)3. Inventory Basic Amino Acids4. Sequence Entire DNA Strand5. Exit2Base Pairs:A-TA-TG-CT-AG-CG-CC-GT-AA-TEND9 base pairs listed.3 trinucleotides listed.What would you like to do?:</td>

  </tr>

 </tbody>

</table>

Here are the runs looking at Inventory Basic (3) and Sequence Entire DNA (4):

<table>

 <tbody>

  <tr>

   <td width="624">What would you like to do?:1. Display Sequencer (Leading Strand)2. Display Sequencer (Base Pairs)3. Inventory Basic Amino Acids4. Sequence Entire DNA Strand5. Exit3Tryptophan: 1 identifiedPhenylalanine: 0 identifiedWhat would you like to do?:1. Display Sequencer (Leading Strand)2. Display Sequencer (Base Pairs)3. Inventory Basic Amino Acids4. Sequence Entire DNA Strand5. Exit4Amino Acid List:LysineTryptophanLeucineTotal Amino Acids Identified: 3What would you like to do?:1. Display Sequencer (Leading Strand)2. Display Sequencer (Base Pairs)3. Inventory Basic Amino Acids4. Sequence Entire DNA Strand5. Exit5DNA removed from memory-bash-4.1$</td>

  </tr>

 </tbody>

</table>

Finally this is if you were going to validate a menu entry.

<table>

 <tbody>

  <tr>

   <td width="624">-bash-4.1$ make run1./proj3 proj3_9.csvNew Sequencer loadedWhat would you like to do?:1. Display Sequencer (Leading Strand)2. Display Sequencer (Base Pairs)3. Inventory Basic Amino Acids4. Sequence Entire DNA Strand5. Exit0What would you like to do?:1. Display Sequencer (Leading Strand)2. Display Sequencer (Base Pairs)3. Inventory Basic Amino Acids4. Sequence Entire DNA Strand5. Exit6What would you like to do?:1. Display Sequencer (Leading Strand)2. Display Sequencer (Base Pairs)3. Inventory Basic Amino Acids4. Sequence Entire DNA Strand5. Exit5DNA removed from memory-bash-4.1$</td>

  </tr>

 </tbody>

</table>

6.  Compiling and Running

Because we are using a significant amount of dynamic memory for this project, you are required to manage any memory leaks that might be created. For a linked list, this is most commonly related to the dynamically allocated nodes. Remember, in general, for each item that is dynamically created, it should be deleted using a destructor.

One way to test to make sure that you have successfully removed any of the memory leaks is to use the <strong>valgrind</strong> command.

Since this project makes extensive use of dynamic memory, it is important that you test your program for memory leaks using <strong>valgrind</strong>:

<strong>valgrind ./proj3 proj3_60.csv</strong>

Note: If you accidently use valgrind make run1, you may end up with some memory that is still reachable. Do not test this – test using the command above where you include the input file.

If you have no memory leaks, you should see output like the following:

<table>

 <tbody>

  <tr>

   <td width="624">==5606====5606== HEAP SUMMARY:==5606==     in use at exit: 0 bytes in 0 blocks==5606==   total heap usage: 87 allocs, 87 frees, 10,684 bytes allocated==5606====5606== All heap blocks were freed — no leaks are possible==5606====5606== For counts of detected and suppressed errors, rerun with: -v==5606== ERROR SUMMARY: 0 errors from 0 contexts (suppressed: 6 from 6)</td>

  </tr>

 </tbody>

</table>

The important part is “in use at exit: 0 bytes 0 blocks,” which tells me all the dynamic memory was deleted before the program exited. If you see anything other than “0 bytes 0 blocks” there is probably an error in one of your destructors. We will evaluate this as part of the grading for this project.

Additional information on <strong>valgrind</strong> can be found here: <a href="http://valgrind.org/docs/manual/quick-start.html">http://valgrind.org/docs/manual/quick-start.html</a>

Once you have compiled using your <strong>makefile</strong>, enter the command <strong>./proj3 proj3_9.csv</strong> to run your program. You can use <strong>make run1</strong>, <strong>make run2</strong>, <strong>make run3</strong>, and <strong>make run4</strong> to test each of the input files. They have differing sizes. If your executable is not <strong>proj3</strong>, you will lose points. It should look like the sample output provided above.

7.  Completing your Project

When you have completed your project, you can copy it into the submission folder. You can copy your files into the submission folder as many times as you like (before the due date). We will only grade what is in your submission folder.

For this project, you should submit these files to the <strong>proj3</strong> subdirectory:

<strong>driver.cpp</strong> — should be unchanged.

<strong>DNA.h</strong> — should be unchanged.

<strong>DNA.cpp</strong> – should include your implementations of the class functions.

<strong>Sequencer.h</strong> — should be unchanged.

<strong>Sequencer.cpp</strong> – should include your implementations of the class functions.

As you should have already set up your symbolic link for this class, you can just copy your files listed above to the submission folder

<ol>

 <li>cd to your project 3 folder. An example might be cd <strong>~/202/projects/proj3</strong></li>

 <li><strong>cp driver.cpp DNA.h DNA.cpp Sequencer.h Sequencer.cpp ~/cs202proj/proj3</strong></li>

</ol>

You can check to make sure that your files were successfully copied over to the submission directory by entering the command

ls ~/cs202proj/proj3

You can check that your program compiles and runs in the <strong>proj3 </strong>directory, but please clean up any <strong>.o </strong>and executable files. Again, do not develop your code in this directory and you should not have the only copy of your program here.

For additional information about project submissions, there is a more complete document available in Blackboard under “Course Materials” and “Project Submission.”

<strong><u>IMPORTANT:</u></strong> If you want to submit the project late (after the due date), you will need to copy your files to the appropriate late folder. If you can no longer copy the files into the proj3 folder, it is because the due date has passed. You should be able to see your proj3 files but you can no longer edit or copy the files in to your proj3 folder. (They will be read only)

<ul>

 <li>If it is 0-24 hours late, copy your files to <strong>~/cs202proj/proj3-late1</strong></li>

 <li>If it is 24-48 hours late, copy your files to <strong>~/cs202proj/proj3-late2</strong></li>

 <li>If it is after 48 hours late, it is too late to be submitted.</li>

</ul>