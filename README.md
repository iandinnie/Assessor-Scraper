# Assessor-Scraper
A web scraper for Vision Government Solutions public assessor record databases
Uses RSelenium drive a remote browser to the webpage for each respective address
Then uses RVest to parse the HTML for each address, creating a list object for each address that contains owner name & address, sales history, and building attributes
This all happens in a function, which is then passed to purrr::map() to create a list equal to the length of the addresses vector that is passed to it
Then condenses the list into three data frames, one for owner info, one for sales history, and one for building attributes and writes to a csv
It is set on a timer to only run for 3 hours at a time, which is optional, I was experiencing a lot of blue-screen errors on my computer (totally non-related to this script)
So I decided to make it run in batches to prevent losing all the data in the event of a blue-screen error while it is running
