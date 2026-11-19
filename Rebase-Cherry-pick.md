

Rebase? 

main ---------------------------------->
                |                      |
                Feature branch --------


Rebase - My branch is behind main branch.
         How do i bring it up to main without adding a merge commit.

Cherry-Pick 





Release_26.11 ---------Improvement in login dashboard --------->Improve logging of error------------> 
                            commit a                                   Commit b


Release_27.3 ---------> Fxing the login issue --------> Encrpyting the password handling--------------->
                            commit c.                           commit d



According to EU - After 27.1, every data should encrypted. 


Cherry-Picking means - picking perticular commit from another branch and merging it to current branch.




Before Rebase:


    A---------- B ------------- C ------------- D. main
                |
                |
                |--------------F1 ------------- F2 Feature.    (Improvement in login)  
                            Add login          fix login
After Rebase:

A ------------- B -------------- C ------------ D --------------F1' -------------- F2' 

Rebase -----> Replays the feature commits on top of newer commit in main branch. 


Git merge vs                    Git rebase

    |                               |
merges two                      on top of newer commit in main, it adds feature commits.
commit histories






Imagine you have created 4 commits:

Add login
Fix login
Fix typo
Final login fix

Do you rellly need these four commits in our pull request? Or we can combine them into one clean commit?

git log --online
git rebase -i HEAD~3


Editor:

pick a1b2c3 add login
pick d4e5f6 fix login
pick a7b8c9 fix typo

Change it:

pick a1b2c3 add login
fixup d4e5f6 fix login
fixup a7b8c9 fix typo

pick ------> Keep commit
reword ----> change commit message
squash ----> combine the commits and edit messages
fixup -----> Combine and discard extra messages
drop ------> Remove commit




Git Tag

Imagine we are working in amazon.

E-cmmerce application developement team.

Monday - we launched version 1.0 to customers

Tuesday, - developers add a new payment feature

Wednesday - Improved the search functionality

Thursday - fixed some bugs

Customer has reported a problem with the app released on Monday.

Manager? what exact code is running in production?

Main branch is already moved ahead. 


How do we identify the exact code we released to customers on Monday?

GIT TAG - A simple name given to a specific commit:


                            v1.0.0
A ----------- B ------------- C -------------- D ------------- E
Inital      Login           Released        Search          Payment
                                                                main

We marked on commit (Given name to a commit) 

Lightweight tag - Name pointing to a commit.


Annotated Tag - Contains additional information like tagger, date, message. It stores this all thing in a seperate git object.


Tags hepls you to easily rollback.

----------------------------------------------
Semantic Versioning

Why do companies give names to their releases as v1.2.3, v2.5.0, v3.0.0

Can they version it like Version A, Version B or Version C?



2.5.3

2 ----> Major (Breaking change) 

5 ----> Minor (New feature)

3 ----> Patch (Bug fix) ----> 


Git tag 

Commit ---- a1b2c3 ---- v2.0.0

Release - Pushing your software for users

Release Pipeline:


1. Finalize the code

2. Decide version number

3. Identify the release commit with a tag.
    v2.0.0

4. Build and test the software

5. Preparing the release notes

6. pushish the deploy

Change Logs:

Version 1.1.0

Added:
    -
    -
    -

Fixed :
    -
    -
    -
    






















