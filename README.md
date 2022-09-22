# 📜Blog Site using SQLite, Flask & Jinja of Python

🌟Previously in Part 2 (https://github.com/bellaryyash23/Blog_Flask_Jinja_2) Upgraded the Blog site with inclusion of Bootstrap & Bootstrap templating. With this 
upgradation in frontend, in the backend the implementation of HTML forms in Flask is done. 

🌟Now, in this version the minor update is done to the styling of the website. The major update in this version is creation of SQLite database 'posts.db' 
for storing the blog's data and use of Wtforms & CKeditor extensions of Flask to add the functionality to edit a particular post & create a new post on the website itself.

🌟Thus, added the ability of forms to be able to cater to GET, POST, PATCH & DELETE methods of form request.

👉The final version of the website after all the upgradation is as follows:

![Upgraded Final Version of Website](https://github.com/bellaryyash23/Blog_Flask_Jinja_3/blob/master/samples/site.gif?raw=true)

👆Final version of website after this Upgrade👆

👉First in the 'main.py' file, the SQLite database 'posts.db' is created with its structure being defined using the SQLAlchemy ORM extension of Flask. Next, the WTForms
structure is defined, which is to be used to create & edit posts.

👉The home route is made to render all the posts from the database using the SQLAlchemy operations. The data is formated in the html file using Jinja templating from
previous version.

![Home Page of Blog site](https://github.com/bellaryyash23/Blog_Flask_Jinja_3/blob/master/samples/home.jpg?raw=true)

👆Home Page of the website👆

👉Each individual post can be viewed separately on its respective page under the show_post route using the post_id to get the appropriate post details. Also, we can view 
the edit button added to each post to be able to edit the post.

![Post Page of Blog site](https://github.com/bellaryyash23/Blog_Flask_Jinja_3/blob/master/samples/post.jpg?raw=true)

👆Post Page of the website👆

👉On the home page, we can find the option to create a new post which the user can tap into, allowing them to make a new post entry to the database. This is done under the
new-post route which uses WTForms created earlier and CKeditor extensions to provide the proper structure to be able to create and format the post to your needs.

👉When the POST request is from the WTForms it is validated in the Flask server route and the data is appended to the database. After which the user is redirected to 
the home route where they can view the newly created post.

![Create a New Post for Blog site](https://github.com/bellaryyash23/Blog_Flask_Jinja_3/blob/master/samples/new_post.jpg?raw=true)

👆Create a New Post for Blog site👆

👉Each post page has a button to edit that post, this allows user to edit the already created posts data. When user presses the edit button, they are redirected to a page
similar to the create-new-post page but, all the fields are prepopulated. Then the user can select the particular field to update and then submit the updated.

👉Since HTML forms (WTForms included) do not accept PUT, PATCH or DELETE methods. Thus this edit request gets passed as a POST request to the server and is updated 
in similar way as a new post request.

![Edit Post Option for Post on Blog Site](https://github.com/bellaryyash23/Blog_Flask_Jinja_3/blob/master/samples/edit_post.jpg?raw=true)

👆Edit Post Option for Post on Blog Site👆

👉Finally, we also have the option to remove/delete a post from the Blog site and consecutively from the database. This option is visible on home page where all the posts
are rendered. It has 'X' symbol in anchor tag with it redirecting to the delete-post route, where the post id is used to delete the post from database.
