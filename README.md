# HSFaces Android App

This is a port of [HSFaces](https://github.com/adamfraser/HSFaces) project.  It's a memory game and Hacker School directory
for former and current students.

# How it works

On begin, you must login with your Hacker School email and password.  This then scrapes the Hacker School website, downloads all the data for each Hacker
School student and saves it to a SQLite database on disk.  Note that if you clear out the data for the app, you'll have to
go through the set up process again.  When a new batch is added, there is an option for refreshing the data from online. Past data
 is not updated unless all data has been cleared out.  

Initial load is quite lengthy (due to XPath processing. This could use some optimization). Most of it is in app processing, 
not data downloaded from the network.

Images are stored locally in internal storage.  This could probably use some more error checking.  Offline play uses only the images that are already stored locally.

## Game Play

Users are shown a randomly selected subset of all Hacker Schoolers.  After a set number of guesses (41 at the moment), 
the game ends.

## Browsing for a Hacker Schooler

This app also provides a directory of Hacker Schoolers.  It's sorted (at the moment) by batch, then name.  If they've provided it online,
this allows you to visit their github, twitter, or email from within the app.  You can drill down to see more details for each 
Hacker Schooler.

# Onward and upward
## Proposed future work

- [x] Use disk based cache for images / allow for 'offline' play
- [ ] Faster XML parsing
- [x] Give users option to play by batch
- [ ] Style toasts to for Correct and Wrong
- [x] add some more custom styling to fonts
- [ ] animations for win
- [ ] User & skill search
- [x] Store user login data (if requested) and high score
- [ ] Display current user's image after they've logged in
- [ ] Better tablet design for list and drill down

## Contributions

Pull requests welcome! Most of this is undocumented, send me a note if anything's super unclear.

## Due Diligence

Commonsguys' [SQLiteCursorLoader](https://github.com/commonsguy/cwac-loaderex/tree/master/src/com/commonsware/cwac/loaderex/acl) that's been reimplemented in this app. 
