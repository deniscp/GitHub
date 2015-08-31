# GitHub

getCommits() fetches and stores informations about every commit committed since a given date for every repository of a given list of repositories. It creates a table named Commits on a given database in which it stores some values: Full_name, Sha, Date, Committed_by, File and Commit. Full name field is in the form "organization name/repository name" (or "user name/repository name"), Commit field contains all informations about the commit.

getIssues() fetches and stores informations in csv files about every issue opened since a given date for every repository of a given list of repositories. Furthermore creates a table named GetIssues on a given database, in which it stores some values: full_name, number, created_at, created_by, state and issue. Full name field is in the form "organization name/repository name" (or "user name/repository name"), issue field contains all informations stored in the csv file.

getLimts() prints the rate limits for accessing GitHub API endpoints.

setUrl() sets a different url of repository.

setDate() sets a different date.

GitHub(String url, GregorianCalendar date) is the default and only constructor. It takes the url of list of repositories and the date of values since you want to print them.


To use Test class with the main method the sintax is the following: "Test https://url dd-MM-yyyy";
url represents the GitHub api https url of the list of organization (or list of user) repositories and dd-MM-yyyy represents the format of the date since commits have been committed.

By default jdbc database url is "jdbc:postgres://localhost:5432/GetIssues" and login and password are set to "postgres" in the openCommitDB() and openIssueDB() methods of GitHub.java.
If you want to use a jdbc driver prior to version 4.0 you will need to uncomment "Class.forName(...)" and "catch(ClassNotFoundException ex){...}" blocks in openCommitDB() and openIssueDB().
