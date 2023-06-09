The primary goal of the web application is to receive input on the user’s end that can help us query for certain anime from our API. User demographics will mostly consist of people who watch anime but we can expect people who may be entering the genre as it is common for newcomers to be given recommendations. The returned output will then be used to curate lists that the user can share, save (to their own page), edit or simply share as is. In addition the user should be able to create their own lists without any particular input but simply by searching for any given anime. 

Database schematics should roughly look like:

```
A users table containing user data. (Since the app is focused on list personalization there will not be much stored in regards to users other than username, password, image, and other commonalities.) Sensitive information will need to be primarily protected here with common security concerns such as cross-site password usage being a risk for users.

An anime table that is updated whenever an anime is chosen to be put on a list but not yet on it. It should default to having content from the API.

A list table that acts as a many-to-many relationship type table, connecting users and anime.
```
The main issue that may arise using this API is failed search queries.

General user flow should begin with the user landing on the home page, and if they are not already logged in then they will be prompted to begin the recommendation process (but have options to be taken to the main page as well). Once the process is done, they can opt to save the list (by creating an account) allowing them to further customize or share the list (list generated by GET request with query parameters for each anime). A navigation bar is at the top of the main page to allow the user to navigate around and perform functions such as login, register, logout, access or create lists. 

