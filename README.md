

<b>Make sure you </b> are in the <b>technologiesoutcomes</b> and while in the <b>technologiesoutcomes</b> directory create a subdirectory called <b>myassignments</b> and change into it.

```
mkdir myassignments

cd myassignments
```

Then clone the repository below into your <b>myassignments</b> subdirectory.
```
git clone https://github.com/techoutcomes/assignments
```
Change into the <b>assignments</b> directory
```
cd assignments
```
Change into the relevant assignment subdirectory. For instance if you want to submit assignment2 work, change into the assignment2 subdirectory.
```
cd assignment2
```

While in <b>assignment2</b> subdirectory, copy the <b>student1</b> subdirectory to a new subdirectory with a name exactly matching your names - the names by which you are known on the platform. No spaces and only use lower case characters. You must retain this naming convention going forward.

For instance if your names were Bob Ndikam, your directory would be called <b>bobndikam</b>
```
cp -R student1 bobndikam
```

This will create a new subdirectory named with your names. Change into your new subdirectory. 
```
cd bobndikam
```
Launch Visual Studio Code.

```
code .
```

Edit the README.md file and add your answers to the assignment questions. Save your work.


<b>Change back to the root of your repository.</b>

```
cd ../../
```

Push your assignment submission to the main GitHub repository.

```
git pull
git add .
git commit -m "bobndikam: My submission for assignment 2"
git push
```

Go and check the GitHub repository and verify that your submission has appeared and is in the right place. If it is, this completes the submission. If not take action to make whatever corrections are necessary.



