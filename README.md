The goal for this project:
    Search through the first 100 hot posts in any subreddit, and count how many times a post mentions specific words.

The requests library was used to extract the specific data source from any subreddit. The user is prompted to type the name of the subreddit as input into the reddit url.
The JSON file that comes with the link for this subreddit provides the textual information of the titles (line 39) and body (line 41) of each post.

Users are prompted to type in keywords they would like to search, populating an empty dictionary.
The for loop (line 38) iterates through the title and body text of each post, numbered 0-99 in JSON. The name_counter function is called.
The name_counter function (line 52) looks for any of the keys from the dictionary in each post. If a key is found, the value of that key is incremented by 1.
To avoid capitalization/matching issues, I converted all the text to lowercase, and matched the text with the dictionary, also lowercased.

After iteration of the first 100 posts, the dictionary with its updated values is returned and inputted into the load_reddit function (line 64).
The load_reddit function takes in the dictionary and populates a csv file with the contents, formatting the keys and its corresponding values per line.

Extract, Transform and Load functions are all called in lines 85, 87, and 88 respectively.
The extract function is called with the name of the subreddit (as it would be in the url) and the amount of posts as a parameter.
The populate function (line 86) returns a dictionary of user input words.
The transform function is called with the extracted raw data as its parameter, equated to a variable.
The load function is called with two parameters: the variable equated to the transform function, and the name for the csv file.

Matplotlib was used to visualize the results of the search via bar graph.

2/5/23: Added posts input into url. Example used: r/nba subreddit, 22 entries.