Homepage (www.domain.com):


	- On page load:
		- Most Followed Lists Widget:
			- Receive from backend:
				- ranked list of "most popular searches" - need to define "most popular"
				- each item will include the list image, title, and description along with the associated ranking - probably only top 10 items

		- Newly Created Lists Widget:
			- Receive from backend:
				- list of 10 most recently created lists
				- each item will include list image, title, and description

	- AJAX:
		- Search Widget:
			- Send to backend on user search:
				- search term(s) for lists that have been created on our site
				- will search lists based on:
					- list title
					- list description
			- Redirect user to dynamically built SRP page




------------------------------------------------------------------------
------------------------------------------------------------------------



SRP - No Results (dynamic URL - www.domain.com/search/query_string):

	- On page load:
		- Receive from backend:
			- user's search term and something to let me know that "0" result were returned


	- AJAX:
		- Search Widget:
			- Send to backend on user search:
				- search term(s) for lists that have been created on our site
				- will search lists based on:
					- list title
					- list description
			- Redirect user to dynamically built SRP page



------------------------------------------------------------------------
------------------------------------------------------------------------



SRP (dynamic URL - www.domain.com/search/query_string):

	- On page load:
		- Receive from backend:
			- user's search term and the results that were found
			- for each item:
				- rank
				- number of upvotes
				- number of downvotes
				- list image
				- list title
				- list description
				- list author



------------------------------------------------------------------------
------------------------------------------------------------------------



Details Page - (dynamic URL - www.domain.com/details/list_title - all list titles will have to be unique)

	-On page load:
		- Receive from backend on page load:
			- list number of upvotes
			- list number of downvote
			- list title
			- list description
			- list author
			- list total number of follows
			- array of each twitter user


	- AJAX:
		- when "Follow All selected" button is click
			- Send to backend:
				- signed in user's twitter name
				- list title for current details page
				- array of new twitter usernames to follow
				- upvote/downvote updates (optional)

				- Once send is complete, receive from backend:
					- list of all successful new follows

		- when "report this list" button is clicked:
			- send to backend:
				- reporter's twitter username
				- list title
				- list author
				- message from user that describes the issue - will be reviewed/handled internally?

		- when "suggest a change to this list" is clicked:
			- send to backend:
				- username of person suggesting change
				- list title
				- array of users to remove
				- array of users to add

			- on successful response from server, confirm to user that DM has been sent and display the contents of the message
				- username of person suggesting change
				- list title
				- array of users to remove
				- array of users to add



------------------------------------------------------------------------
------------------------------------------------------------------------



Profile Page - (www.domain.com/profile/twitter_username)

	- On page load
		- Twitter user info widget:
			- Recieve from backend:
				- profile image
				- profile username
				- profile real name
				- profile description

		- Lists you've created widget:
			- for each list item:
				- number upvotes
				- number downvotes
				- list image
				- list title
				- list description

		- Lists you've followed widget:
			- for each list item:
				- number upvotes
				- number downvotes
				- list image
				- list title
				- list description
				- list author


		- AJAX
			- When "unfollow" button is clicked
				- send to backend:
					- list title that was unfollowed

				- on successful response from server, confirm to user with list of twitter usernames that were successfully unfollowed


			- When "delete" button is clicked
				- send to backend:
					- list title to remove from database/make inactive

				- on successful response from server, confirm to user that list has been deleted and remove from "Lists you're created"




------------------------------------------------------------------------
------------------------------------------------------------------------



Create New List - (www.domain.com/create/list)



	- AJAX:
		- when user blurs the list title field:
			- send to backend:
				- list title to find out if this title has already been taken
			- on successful response from server, give the user appropriate feedback regarding list title validitity

		- when user hits spacebar/enter in search field:
			- send to backend:
				- text value of search input
			- on successful response from server, update content in "Results" box
				- for each user that's returned:
					- twitter image
					- twitter username
					- twitter real name
					- twitter description

		- when "create list" button is clicked:
			- send to backend:
				- user creating this list
				- list title
				- list image
				- list description
				- array of usernames to associate with this list
				- boolean value for allowing suggestions from other users






