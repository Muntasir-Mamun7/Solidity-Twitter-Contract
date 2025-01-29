This smart contract allows users to create, like, and unlike tweets while ensuring compliance with constraints set by the contract owner. The project aims to explore blockchain-based social media solutions by leveraging decentralization, immutability, and transparency.


# Deployed Contract(Output)

 ![image](https://github.com/user-attachments/assets/fa27ab00-3732-4a33-8df1-de193cc2f07e)

 ![image](https://github.com/user-attachments/assets/5baba66d-2393-4b04-a5a9-70c4310d9e27)
 
# Contract Structure
The smart contract is written in Solidity and consists of the following key components:
#	Global Variables:
o	MAX_TWEET_LENGTH: Defines the maximum length of a tweet, initially set to 280 characters. The contract owner has the authority to modify this value.
o	owner: Stores the address of the contract owner, granting them exclusive privileges.
#	Data Structure:
o	Tweet struct: Represents each tweet with the following attributes:
	id: Unique identifier for the tweet.
	author: Address of the tweet creator.
	content: The tweet's text.
	timestamp: Records the time of creation.
	likes: Tracks the number of likes the tweet has received.
o	tweets: A mapping (mapping(address => Tweet[])) that stores arrays of tweets associated with each user.
Functions Implemented
#	Constructor:
o	Initializes the contract and assigns ownership.
•	Modifiers:
o	onlyOwner: Restricts certain functions to the contract owner.
#	Core Functions:
o	changeTweetLength(uint16 newTweetLength): Allows the owner to modify MAX_TWEET_LENGTH.
o	createTweet(string memory _tweet): Enables users to post tweets while ensuring they adhere to the character limit.
o	likeTweet(address author, uint256 id): Increments the like count of a specified tweet.
o	unLikeTweet(address author, uint256 id): Decrements the like count, ensuring it does not fall below zero.
o	getTweet(uint _i): Retrieves a specific tweet based on its index.
o	getAllTweets(address _owner): Returns all tweets associated with a given user.
# Deployment and Testing
The contract was deployed using Remix, and all interactions were tested via its built-in UI. Screenshots of the deployed contract and function executions were captured and attached.
#Key Observations:
1.	Functionality Verification:
o	The contract successfully enforces the tweet character limit and prevents exceeding MAX_TWEET_LENGTH.
o	Users can create tweets, and all tweets remain retrievable via getTweet and getAllTweets.
o	Likes and unlikes operate as expected, ensuring proper constraints.
2.	Dynamic Parameter Adjustment:
o	MAX_TWEET_LENGTH was modified from 280 to 400 via changeTweetLength, demonstrating correct owner privileges.
o	The new value was accurately reflected in the contract state and enforced for subsequent tweets.
# Error Handling & Security Considerations:
•	The contract prevents tweets from exceeding the character limit.
•	The likeTweet and unLikeTweet functions ensure that likes are not decremented below zero.
•	Access control mechanisms ensure that only the owner can modify MAX_TWEET_LENGTH.4

This project represents a significant step in exploring decentralized applications (DApps) using Solidity. The contract is fully functional, demonstrating key social media features in a decentralized context. Future enhancements will focus on security, scalability, and real-world applicability. Ongoing improvements and refinements will contribute to the research paper, aligning with broader objectives in blockchain-based social media solutions.
