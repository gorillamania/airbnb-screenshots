# Pull Airbnb Screenshots

Tool to grab pages in bulk from Airbnb for auditing purposes, for Airbnb employees only. Read: it won't work unless you have an internal airbnb login.

## Installation
There are a few dependencies to set up. This is a one time set up for each computer.

### Dependencies
1. Brew (to install node.js and other goodies). To install brew, open up Terminal and run: `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`, and follow any remaining instructions.
2. Install node with `brew install node`. To confirm it worked, run `node -v`


### Installing airbnb-screenshots
1. Clone this repository by running `git clone https://github.com/gorillamania/airbnb-screenshots.git` Note: if you haven't installed `git` yet, you will be prompted with instructions on how to do so
2. Run `npm install` to install the required packages



## Usage
Once you have it installed, you run it by passing the input file and output directory. The input file is a CSV file with reservation ids, one per line. The output directory is where you want the files saved. 


#### Chrome Extension for getting Airbnb 
 
The tricky part to getting this to work was passing the login cookies to the browser that is doing the screenshots. The solution (if you can call it that) that I used was to use a Chrome Extension called [Cookie Inspector](https://chrome.google.com/webstore/detail/cookie-inspector/jgbbilmfbammlbbhmmgaagdkbkepnijn?hl=en). It has an export that will give you all the cookies for a given website. 

To get your Airbnb cookies:

1. Install Cookie Inspector chrome extension
2. Visit airbnb.com. Log in. 
3. Open the developer console (View -> Developer Tools -> Javascript Console)
4. Click on Cookies

#### Running
1. Create the CSV file with the reservervation ids. 1 column. For a sample format, see [media/sample.csv](media/sample.csv)
2. From terminal, cd into the directory where you cloned the repository (`cd airbnb-screenshots`) and run `./grab --cookie-jar=$cookieFile $inputfile $outputDir`, where $cookieFile is the file you exported from the Cookie Inspector, $inputFile is the CSV you created, and $outputDir is the directory where you want to have the files saved. 
