## Welcome to Wiki trivia game!
   ###This is a trivia game based on data gathered from Wikipedia API (wikidata).
   
   ###NOTICE: The wptools wrapper and the wikipedia api python wrapper are required to run the program. Links are inluded below in the in depth documentation.
     
   ###You can enter keyword in the game to decide what kind of informaton you want to guess, and you can also choose the difficulity levels to chanllage yourself!
     
   ###You will have 5 chances to play and there is a time count in the game based on system time.
     
   ###After palying, you can see your ranking.
   
   ###In-Depth Documentation:
   	This program uses the Wikipedia API, Wikimedia, to make a text-based  trivia/flashcard style game in the console where the user can choose what they want to be quizzed on. The user inputs various names (preferably the names of historical figures, using names from landmarks, things, and fictional people caused some problems). These names are searched on Wikipedia for their closest matching page, and the title of each page is extracted into a list. This is done with the Wikipedia python wrapper, found at https://github.com/barrust/mediawiki. This wrapper is then used to extract the summary from the page with the corresponding title, and stores this summary in another list. There is a difficulty function that changes the number of sentences extracted from each summary. These summaries act as the “questions” in the game, so the more sentences extracted, the easier it is to guess the matching individual. Once both of these are in separate lists, we extracted the wikidata from each page using the wptools python wrapper, found at  https://github.com/siznax/wptools. From this data, we extracted the “aliases” for each item. The aliases are all the names/nicknames of the individual the user asked for. Once we had this data, we replaced each instance of an alias with question marks, so the user will have to guess who the summary is describing. 
	With all the data extracted from the API, we used another function to turn it into questions. The function goes through a dictionary where the keys are the summaries and the values are the titles. The user is given each summary with the names in it obscured and has to input the correct matching name. Once they get it right, key/value pair is deleted from the dictionary to prevent it from being prompted again, and the user moves on to the next question until all are answered. We also added a function that keeps track of how long the user had been playing the game.
BUGS:  I would like to note that there are some slight faults in our code. For example, we could not figure out how to prevent the API wrapper from printing gathered data in the console, each time data is extracted, lines of various wikidata print to the console. This isn’t game breaking, but is an aesthetic issue. It is also worth noting that the game does not work very well with fictional characters, as they often do not have wikidata aliases like a real historical figure. If a user entry does not have aliases associated with it, and error appears. Finally, we had to split the words of each alias, as there were some instances of aliases being found in aliases in the summary. This prevented the outer alias from being obscured, so instead we obscured each instance of an alias word.  This created the problem of aliases containing common words like “the”, “of”, and “and”, as we did not want them from being obscured in the rest of the summary. To prevent this, we made a list of common words that were not to be hidden.
	











































