put the mogodb atlas link in the .env file

1: first we have to register a user by sending a POST request: http://localhost:8800/api/auth/register
username:
email:
password:

2: login that user by sending POST request: http://localhost:8800/api/auth/login
    email:
    password:

if we send the wrong details it will show 400 bad request wrong password or wrong email

3: update the user we can update a user by sending a PUT request: http://localhost:8800/api/users/userId

we can update the user info by sending request if the request is fulfilled succesfully then it will send reponse with status code 200
if the user want to update the other user then it will send the status code 403 with response that you can update your account only

4: delete a User by sending DELETE request: http://localhost:8800/api/users/(put user id here)userid

In the body part use JSON property and send the userId in JSON format then user will delete.

5: we can find a user by sending a GET request: http://localhost:8800/api/users/userid(from user collections)
if the user is not found or any error happend it will return status Code 500 

6:  we can follow any user by sending a PUT request: http://localhost:8800/api/users/userid/follow
 in body we put the userId of another user whom we want to follow after the following equest send it will send the status code 200 with reponse
 that user has been followed if the user is already followed then  it will say you already follow this user with status code 403
 and if a user want to follow itself by sending his own id then it will say you can not follow yourself with status code 403 forbidden

7: same goes with unfollow we send a PUT request: http://localhost:8800/api/users/userID/unfollow
if we send the request to unfollow a user then in body selecting JSOn we put a userID of whom we want to unfollow then  it will unfollow that user if you are following him by sending status code of 200.
If you don't follow that user then it will send you the reponse that you don't follow this user by status code 403
And if user sending it's own userId then reponse will be you can not unfllow yourself with status code 403.

Creating Posts

1: we can create any post by seding POST request: http://localhost:8800/api/posts
in body part in JSon format we put our userID then we can post after creating the post it will send the status code 200

2: we can update our post by sending PUT request: http://localhost:8800/api/posts/Id(622b37618241705ee4f0345d) in this link we provide the id from the post collection not the user collection.
in the body part with JSON format we provide  userID from post collection and the thing we want to change about our post after updating the post it will send the reponse the post has been updated with status code 200 otherwise if we give a wrong ID or other persns id then it will send the reponse that you can update only your post with status code 403.

3: we can delete any post by sending the DELETE request: http://localhost:8800/api/posts/postid(622b37618241705ee4f0345d) in this link we provide the id from the post collection not the user collection.

in the body part we send the userId from that post from post collection and we send a request if it is fullfilled then it will send the response that you can delete only your post and if we provide wrong ID then it will send the reponse that you can only delete your post only with status code.

4: like/dislike a post by sending a PUT request: 
http://localhost:8800/api/posts/622b37a98241705ee4f03461(this is a dummy id here we put  id from post collection)/like
in body we send the user id for that post and this userID we can get from post collection
if the post hasn't been liked before then it will send the reponse that the post has been liked and the post was liked before then it will send the reponse that the post has been disliked with status code 200.

5: We can see any post by sending the GET request:
http://localhost:8800/api/posts/622b37a98241705ee4f03461(this is a dummy id here we put  id from post collection)

by sending the request we can see the post and details about it.

6: we can get the timeline by sending GET request: 
http://localhost:8800/api/posts/622b37a98241705ee4f03461(this is a dummy id here we put  id from post collection)/timeline/all
 in body part we provide the userID from the post collection to see his/her timeline the moment we send the request it will show us the timeline feed of user and it's friends.