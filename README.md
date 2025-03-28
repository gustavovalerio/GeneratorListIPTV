# GeneratorListIPTV
M3u8 playlist generator for SSIPTV, Perfect Player and Kodi [and compatibles]  
By Gustavo Valério -> www.gustavovalerio.com.br


**Generate your m3u8 playlists from organized files.**


* Change the **LOCAL_URL** to your **LOCAL IP**.
* If you are not going to use a public list with a different URL, set **ENABLE_LIST_PUBLIC** to False.
* To use a public list with a URL other than **URL_LOCAL**, keep **ENABLE_LIST_PUBLIC** *True* and set **URL_PUBLIC** pointing to the correct domain.
* It is necessary to have **FFMPEG** installed on the machine for the script to work properly.
* It is necessary to have **busybox** with **httpd module** for use with internal fileserver.



### Setting up a directory for Movies


The correct structure, so that the covers are used correctly, should look like this:

  * Inside your movie directory there should be a hidden directory called ".covers". 
  * The extension of the covers must be "jpg". JPEG, PNG or others will not work.  
  * The covers inside the "covers" directory must have the exact same name as the movie to which it belongs, which is in the top directory.  
  * Movies must be in "mkv" format. This format was chosen because it is possible to transmit several subtitles and audios in the same file.

![Movies](https://raw.githubusercontent.com/gustavovalerio/GeneratorListIPTV/refs/heads/main/Imagens/Movies-Example.jpg)
 
### Setting up a directory for your favorite series
* The "Series" directory will contain all series directories.
* Each series directory must contain the directories of their respective seasons.
* Each season directory must contain a hidden "jpg" file named ".cover.jpg". This file is the cover of the season it belongs to.
* The ".cover.jpg" file will be used as the cover for all episodes of the same season.
* Episodes can have any name. Its extension must be MKV, the extension chosen because it allows the transmission of several subtitles and audio files.

![Series](https://raw.githubusercontent.com/gustavovalerio/GeneratorListIPTV/refs/heads/main/Imagens/Series-Example.jpg)

### About Covers

The script defines whether it will render the directory with the settings for movies or series depending on the existence of:
* .covers/
* .cover.jpg

If the cover directory exists, it means that for each ".mkv" file contained in it, there will be a jpg image with the same title/name inside the ".covers/" directory.

If the ".covers/" directory is not found, the script will test if a ".cover.jpg" image exists, if it does, it will set that file as the cover for all ".mkv" files in the same directory.

### To add directory
`./GeneratorM3U8 --add /path/to/directory`

### To load menu and options
`./GeneratorM3U8`

### Help on terminal
```

        -i path-to-dir,
        --add path-to-dir
                               Add directory to list.


        -c, --check
                               Check config files.

        -s, --server
                               Start Busybox HTTP Server.

        -u, --update
                               Update list selected [1,2,3,4]
                               or all [A].

        -d, --delete
                               Delete list selected [1,2,3,4]
                               or all [A].
```




### Images Examples

#### Include Paths (`-add /path/to/file` or `-i /path/to/file`)
![Include](https://raw.githubusercontent.com/gustavovalerio/GeneratorListIPTV/refs/heads/main/Imagens/Example-include.jpg)

#### Lists Menu
![Menu](https://raw.githubusercontent.com/gustavovalerio/GeneratorListIPTV/refs/heads/main/Imagens/Example-menu.jpg)

#### Update List (`-u 2` or `--update 2`)
![Update List](https://raw.githubusercontent.com/gustavovalerio/GeneratorListIPTV/refs/heads/main/Imagens/Example-update-one.jpg)

#### Remove List (`-d 1` or `--delete 1`)
![Remove List](https://raw.githubusercontent.com/gustavovalerio/GeneratorListIPTV/refs/heads/main/Imagens/Example-remove-one.jpg)

#### Update All Lists (`-u A` or `--update A`)
![Update All Lists](https://raw.githubusercontent.com/gustavovalerio/GeneratorListIPTV/refs/heads/main/Imagens/Example-update-all.jpg)

#### Remove All Lists (`-d A` or `--delete A`)
![Remove All Lists](https://raw.githubusercontent.com/gustavovalerio/GeneratorListIPTV/refs/heads/main/Imagens/Example-remove-all.jpg)
