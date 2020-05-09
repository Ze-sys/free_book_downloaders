# free_book_downloaders

# this script downloads the free books Springer provided directly into path ~/Download/Springer_Books/ on a Linux machine. It should work fine on a windows machine with minor adjustments.
                              ## The main task here was consturcting a downloadable url from doi's. After that step, I tested two ways of downloading: (a) Perl's own getstore  and  (b) the system's curl. 
                              ## As expected, getstore is much faster. However, neither tends to download all books. This could be due to timeout setting, that I intend not to delev due to other time commitments.
                              ## As a solution In order to download all books, I am saving the book names and url's  in a plain text file called "url_list" and saving it in the same directory as the books are being downloaded so I can use its contnts with curl later. 
                              ## Update: Using the url_list file I was able to download a lot more (381 vs 67) books. The shell script I used for this task is called "force_download". 

##USAGE: Simply run the script as ./download_springer
        ## if you waould like to use the script force_download, do the same thing. But remember this script won't have the information it needs if you run it before the first script (i.e., download_springer)
## This script is inspired by more elaborate and probably more elegant python script by Alex (https://github.com/alexgand/springer_free_books). There's also R based script somewhere. 
## I just love keeping my Perl skill alive and love exploring things, espicially at this time where I cannot play or watch sports.
