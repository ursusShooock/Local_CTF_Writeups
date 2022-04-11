We are given a .wav file
It is a  audio  with distorted audio in between. On checking the spectrogram, we get a pastebin link.

On checking the pastebin link, we have a large dump of hex data.
Saving the file, it does not open directly.  Checking the data on sites such as Cyberchef or using binwalk reveals that the file is a .jpeg.

Changing the header bits to the correct format aka the magic bytes (you can check this out [here](https://en.wikipedia.org/wiki/List_of_file_signatures)), we get an image, a Garfield comic strip.


We see that the flag is visible in the comic strip, however it is encoded.

Now there are a couple of ways to move forward from this point. The challenge name is a reference to the cipher used,
However this is not the only intended approach as this might be a bit far fetched.

From this point, an approach which can be used is to find the date of the comic strip (hinted towards by the crossed out words except the word “date”), which is 21st April, 1989, which is the key (21041989) for the Gronsfeld cipher used.

The ideal approach would be to make use of the standard flag format being known (INSEC{}), which is seen in the image, albeit encoded. 
Analyzing this, we can decrypt it as a Vigenere cipher with the key “grons”, from which we get the flag.

