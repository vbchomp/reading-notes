# Class 09 - Forms and Events

[<== Main Page](../README.md)

## *HTML Book* Chapter 7

```render-html
<!DOCTYPE html>
<html>

<head>
<title>repl.it</title>
<link href="style.css" rel="stylesheet" type="text/css" />
</head>

<body>
<form action="http://www.example.com/subscribe.php" method="get">
<p>This is where the form controls will appear.</p>
<!-- INputting text -->
<form action="http://www.example.com/login.php">
<p>Username:<input type="text" name="username" size="15" maxlength="30"/></p>
<!-- Inputting passwords -->
<p>Password:
  <input type="password" name="password" size="15" maxlength="30" />
  </p>
</form>
<!-- Text area for comments -->
<form action="http://www.example.com/comments.php">
  <p>What did you think of this gig? </p>
  <textarea name="comments" cols="20" rows="4">Enter your comments...</textarea>
</form>
<!-- Radio buttons -->
<form action="http://www.exmaple.com/profle.php">
  <p> Please select your favorite genre:
  <br />
  <input type="radio" name="genre" value="rock" checked="checked" /> Rock
  <input type="radio" name="genre" value="pop" /> Pop
  <input type="radio" name="genre" value="jazz" /> Jazz
  </p>
</form>
<!-- Check boxes -->
<form action="http://www.example.com/profile.php">
  <p>Please select your favorite music service(s):
  <br />
  <input type="checkbox" name="service" value="itunes" checked="checked" /> iTunes
  <input type="checkbox" name="service" value="lastfm" /> Last.fm
  <input type="checkbox" name="service" value="spotify" /> Spotify
  </p>
  </form>
<!-- Drop down lists -->
<form action="http://example.com/profile.php">
  <p> What device do you listen to music on?</p>
  <select name="devices">
    <option value="ipod">iPod</option>
    <option value="radio">Radio</option>
    <option value="computer">Computer</option>
  </select>
</form>
<!-- Selecting multiple in drop down list -->
<form action="http://www.example.com/profile.php">
  <p> Do you play any of the following instruments? (You can select more than one option by holding down the control on a PC or the command key on a Mac while selecting different options.)</p>
  <select name="instruments" size="3" multiple="multiple">
    <option value="guitar" selected="selected">Guitar</option>
    <option value="drums">Drums</option>
    <option value="keyboard" selected="selected">Keyboard</option>
    <option value="bass">Bass</option>
  </select>
  </form>
<!-- File uploads -->
<form action="http://www.example.com/upload.php" method="post">
  <p>Upload your song in MP3 format:</p>
  <input type="file" name="user-song" /><br />
  <input type="submit" value="Upload" />
</form>
<!-- submit buttons -->
<form action="http://www.example.com/subscribe.php">
  <p>Subscribe to our email list:</p>
  <input type="text" name="email" />
  <input type="submit" name="subscribe" value="Subscribe" />
</form>
<!-- image buttons -->
<form action="http://www.example.com/subscribe.php">
  <p>Subscribe to our email list:</p>
  <input type="text" name="email" />
  <input type="image" src="images/subscribe.jpg" width="100" height="20" />
</form>
<!-- Buttons and hidden controls like bookmarks -->
<form action="http://www.example.com/add.php">
  <button><img src="images/add.gif" alt="" width="10" height="10" /> Add</button>
  <input type="hidden" name="bookmark" value="lyrics" />
</form>
<br/ >
<br/ >
<!-- Label controls -->
<label>Age: <input type="text" name="age" /></label>
<br/ >
<input id="female" type="radio" name="gender" value="f">
<label for="female">Female</label>
<input id="male" type="radio" name="gender" value="m">
<label for="male">Male</label>
<br />
<br />
<!-- Grouping elements into one form-->
<fieldset>
  <legend>Contact details</legend>
  <label>Email:<br />
  <input type="text" name="email" /></label><br />
  <label>Mobile:<br />
  <input type="text" name="mobile" /></label><br />
  <label>Telephone:<br />
  <input type="text" name="telephone" /></label><br />
</fieldset>
  <br />
  <br />
<!-- HTML5 form validation -->
<form action="http://www.example.org/login/" method="post">
  <label for="username">Username:</label>
  <input type="text" name="username" required="required" /><br />
  <label for="password">Password:</label>
  <input type="password" name="password" required="required" />
  <input type="submit" value="Submit" />
</form>
<br />
<br />
<!-- HTML5 date input -->
<form action="http://www.example.org/bookings/" method="post">
  <label for="depart">Departure date:</label>
  <input type="date" name="depart" />
  <input type="submit" value="Submit" />
</form>
<br />
<br />
<!-- HTML5 email and url input -->
<form action="http://www.example.org/subscribe.php/">
  <p>Please enter your email address:</p>
  <input type="email" name="email" />
  <input type="submit" value="Submit" />
</form>
<form action="http://www.example.org/profile.php/">
  <p>Please enter your website address:</p>
  <input type="url" name="website" />
  <input type="submit" value="Submit" />
</form>
<!-- HTML5 Search input -->
<form action="http://www.example.org/search.php/">
  <p>Search:</p>
  <input type="search" name="search" />
  <input type="submit" value="Submit" />
</form>
<form action="http://www.example.org/search.php/">
  <p>Search:</p>
  <input type="search" name="search" placeholder="Enter keyword" />
  <input type="submit" value="Submit" />
</form>    
</body>
</html>
```
