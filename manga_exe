#!/bin/bash
manga_img_downloader(){
manga_name_chapter=$(echo $1 | cut  -d '/' -f 5)
TMPFOLDER=$HOME/.cache/manga-cli/TMPFOLDER
curl -s $1 | rg -o 'http.*.(jpg|png)' | sed -En '/<img/s/.*src="([^"]*)".*/\1/p' | aria2c -i - -c -x 16 -j 2 -d $TMPFOLDER/$manga_name_chapter/
img2pdf $(exa $TMPFOLDER/$manga_name_chapter/*) -o $HOME/.cache/manga-cli/${manga_name_chapter}.pdf && rm -r $TMPFOLDER/$manga_name_chapter

}
manga_img_downloader(){
manga_name_chapter=$(echo $1 | cut  -d '/' -f 5)
TMPFOLDER=$HOME/.cache/manga-cli/TMPFOLDER
curl -s $1 | rg -o 'http.*.(jpg|png)' | sed -En '/<img/s/.*src="([^"]*)".*/\1/p' | aria2c -i - -c -x 16 -j 2 -d $TMPFOLDER/$manga_name_chapter/
img2pdf $(exa $TMPFOLDER/$manga_name_chapter/*) -o $HOME/.cache/manga-cli/${manga_name_chapter}.pdf && rm -r $TMPFOLDER/$manga_name_chapter

}

only_rg_manga_img_downloader(){
manga_name_chapter=$(echo $1 | cut  -d '/' -f 5)
TMPFOLDER=$HOME/.cache/manga-cli/TMPFOLDER
curl -s $1 | rg -o 'http.*.(jpg|png)'  | aria2c -i - -c -x 16 -j 2 -d $TMPFOLDER/$manga_name_chapter/
img2pdf $(exa $TMPFOLDER/$manga_name_chapter/*) -o $HOME/.cache/manga-cli/${manga_name_chapter}.pdf && rm -r $TMPFOLDER/$manga_name_chapter

}
# echo "insert manga link"
# read -r manga_link
# manga_img_downloader $manga_link
# echo "DOne"
# TMPFILE=$(mktemp /tmp/imgall-XXXXXXX)
# curl -s $manga_link | sed -En '/<img/s/.*src="([^"]*)".*/\1/p' | aria2c -i - -c -x 16 -j 2
# aria2c -i $TMPFILE -j2 -d $TMPFOLDER/$manga_name_chapter/
# echo ${manga_link_without_ch_number}${n}



echo "manga link execpt the chapter number:"
read -r manga_link_without_ch_number
for n in {100..135};
do 
  manga_link=$(echo ${manga_link_without_ch_number}${n})
  # manga_img_downloader $manga_link
#  only_rg_manga_img_downloader $manga_link
echo $manga_link
done
echo "Done"
