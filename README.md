# Assignments

## Submitting your assignment 

### Method A - Submitting to the TechnologiesOutcomes GitHub repository (Preferred approach)

<b>Make sure you </b> are in the <b>technologiesoutcomes</b> and while in the <b>technologiesoutcomes</b> directory create a subdirectory called <b>myassignments</b> and change into it.

```
mkdir myassignments

cd myassignments
```

Then clone the repository below into your <b>myassignments</b> subdirectory.
```
git clone https://github.com/technologiesoutcomes/assignments
```

Then create a branch for your assignment using your names and the assigment number. So if your name is <b>Bob Ndikam</b> and your are doing <b>assignment2</b> you will create the branch as follows. 

```
git checkout -b bobndikam-assignment2
```

Verify that you are sitting on the newly created branch.

```
git branch
```
You should see that your branch is displayed with a star.


Change into the <b>assignments</b> directory
```
cd assignments
```
Change into the relevant assignment submissions subdirectory. For instance if you want to submit assignment2 work, change into the assignment2 submissions subdirectory as follows;
```
cd assignment2/submissions
```

While in <b>assignment2/submissions</b> subdirectory, copy the <b>student1</b> subdirectory to a new subdirectory with a name exactly matching your names - the names by which you are known on the platform. No spaces and only use lower case characters. You must retain this naming convention going forward.

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

git add .
git commit -m "bobndikam: My submission for assignment 2"
git push
```

Go and check the GitHub repository and verify that your submission has appeared and is in the right place. If it is, this completes the submission. If not take action to make whatever corrections are necessary.


### Method B - Submitting to your personal GitHub repository 


1) Create a repository in your GitHub called "assignments" and make a note of its address.

2) Clone the technologiesoutcomes assignments repository

git clone https://github.com/technologiesoutcomes/assignments.git

3) Do the assignments in the relevant assignment directory in your local repository.
When you are ready to push, you should push to your own GitHub repository. 

To push to your own GitHub you will have to change the push address of your local repository.
Change the push address as follow. Change the ???????? below to your GitHub account name.

git remote set-url --add --push origin https://github.com/???????/assignments.git

4) Then run the commands to push

git add .
git commit -m "My submission for assignments"
git push

5) Regularly refresh your repository as follows:

git pull

6) Post the link of the assignments on the whatsapp group.



