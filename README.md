# free_book_downloaders

Two scripts are provided to help download the free books Springer provided during the COVID-19 lockdown. Thanks Springer.

# download_springer

The script "download_springer"  downloads  381 pdf books directly into path ~/Downloads/Springer_Books/ on a Linux machine. It should work fine on a windows machine with minor adjustments. However, there are probably easier alternatives for windows users. 

The first task here was consturcting a downloadable url from doi's in this spreadsheet https://resource-cms.springernature.com/springer-cms/rest/v1/content/17858272/data/. When you click on this link it downloads a spreadsheet named "Free+English+textbooks.xlsx". I tested two ways of downloading the books: (a) Perl's own getstore  and  (b) the system's curl.

As expected, getstore is much faster. However, neither option tends to download all books. This could be due to timeout setting that I do not intend to work on soon due to other time commitments.

As a solution to incomplete downloading, the first script is made to save the book names and constructed url's into a plain text file called "url_list" in the same directory (~/Downloads/Springer_Books/). This list will be used by another script called  "force_download" to complete the download.

# force_download
This is a bash script but it has a perl command inside to manipulate some strings. As the name implies, it forces all the stalled downloads to complete by using the "url_list" file. 

# USAGE: 
First go to where you downloaded the scripts and run the script "download_springer" as
```
./download_springer
```
If it complains, try giving it permission by typing:  
```
chmod +x download_springer 
```
in your terminal and try again. 
If you need to install dependancies, follow the output on your screen to guid you install them.

If all goes well, check if all the books are downloaded. If yes, that's it. Happy reading. If the download is incomplete, follow the next simple step.

run the script "force_download" as
```
./download_springer
```
If it complains, try giving it permission as  may have done for the first script and try again.
Remember this script won't have the information it needs if you run it before the first script (i.e., download_springer)

I hope someone will find this useful. 
