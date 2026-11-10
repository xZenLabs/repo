# Classics Cover KOReader Plugin
# Auto-Generate & Apply Book Covers (Tested on Kindle Paperwhite 12, KOReader 2026.03)
-----
## Fan fiction, missing covers, or blurry book cover? Fix them with Classics-style covers directly in KOReader.

<img width="1920" height="1080" alt="Untitled design" src="https://github.com/user-attachments/assets/c6f8e209-4ef9-4e0f-98cd-b5887908fe92" />



## 📚 Classics Cover Generator. How It Works
1. Make sure your device is connected to the internet
2. Long-press the book you want to book cover changed.
3. Tap **“Classics Cover”**
4. Choose a background image  (make sure you already copied the image to /koreader/backgrounds)
5. Confirm or edit the book title and author
6. Tap **Generate**
7. Wait until you see the notification: _“Cover image applied”_
8. Done 🎉
   
## Installation
-----
1. Download the Zip Below
2. Extract and copy the classicscover.koplugin folder to your device's plugins/ directory
3. Restart KOReader and go to **Menu -> Tools -> Classics Cover Generator** to change the settings.
   
## Technical Details:
This plugin sends the book title, author, and selected background image to a Python server (hosted on PythonAnywhere, free plan).  
The server generates the cover and sends it back to KOReader, where it is applied automatically.
