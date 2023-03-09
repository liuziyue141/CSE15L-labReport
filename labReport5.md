```
CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'
rm -rf student-submission
git clone $1 student-submission
echo 'Finished cloning'
cp ./TestListExamples.java ./student-submission/
cp -r ./lib ./student-submission/
echo 'Finished copying'
cd student-submission
if [[ -f ListExample.java ]]
then
    echo 'ListExample.java not found'
    exit 1
fi 
javac -cp $CPATH *.java
if [[ $? -ne 0 ]]
then
    echo cannot compile
    exit 1
fi
java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > error.txt
echo -e '' >> error.txt
cat error.txt
NotPassed=`sed -n '2p' error.txt | grep -o 'E' | wc -l`
TotalTester=`sed -n '2p' error.txt | grep -o '\.' | wc -l`
Passed=$(($TotalTester-$NotPassed))
printf "Correct:   %d\n" $Passed
printf "Incorrect: %d\n" $NotPassed
printf "grade:     %d/%d\n" $Passed $TotalTester
```

* This is a bash script that allows the user to input a git link for cloning. It will then clone the repository into a subdirectory named student-submission and add the JUnit library to the directory. 
* In the student-submission directory, the ListExamplesTest will be compiled and run. The script will save the standard error and standard output of this process into a file named error.txt.
* To obtain the number of errors and tests, the script will use the sed command to extract the second line of error.txt and print each occurrence of "E" and "." on separate lines. The number of lines with "E" and "." are then counted using the grep -o and wc -l commands.
* To calculate the number of passed tests, the script uses arithmetic expansion with the $(($TotalCount - $notPassed)) to subtract the number of passed from the total number of tests. 
* Finally, the printf command is used to print the results in a more readable format compared to using echo.

Here is a screenshot of the tester file:
![tester](image.jpg)
## Corrected Implementation:
	![correct](correct.jpg)
## Partial correct Implementation with logic bug:
	![pc1](pc1.jpg)
	![pc2](pc2.jpg)
## Implementation with compile error:
 	![ce1](ce1.jpg)
	![ce2](ce2.jpg)
	![ce3](ce3.jpg)
 	![ce4](ce4.jpg)
 	![ce5](ce5.jpg)
