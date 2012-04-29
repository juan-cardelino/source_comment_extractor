source_comment_extractor
========================

A small set of tools to extract comments interleaved with code, and generarte documentation.

Existing tools like doxygen or javadoc only allow you to extract the comments that explain the declaration of a function/method, i.e. what the function DOES but not HOW it accomplishes the task.
While that's very useful for most of the regular cases, there are some cases, like the explanation of examples of a certain library, where one needs to describe HOW the code works, line by line or block by block.
In addition, sometimes is useful to extract the comments along with the code, which is another thing most tools doesn't perform.

The aim of these tools is to extract comments from the code, allowing them to have math written in latex, and output a latex (and doxygen in the future) file to be compiled in a documentation.

The original scripts where written by the ITK team for their SoftwareGuide, so most of the credit goes to them.

Requirements
============

* scripts: you need perl installed to generate the latex output
* latex: the latex output is standard, so you need a latex distribution and the listings package available. If you dont want to use listings, it can be disabled in the perl scripts.
 

Instructions
============

generate latex
./ParseCxxExamples.pl DeformableRegistration1.cxx DeformableRegistration1.tex
edit master document hdr_example.tex to include DeformableRegistration1.tex
run latex
pdflatex hdr_example.tex

You can see an example ouput in the file hdr_example.pdf