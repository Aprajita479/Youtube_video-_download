# YouTube Video Downloader Application

This is a simple YouTube video downloader application built using Python's `tkinter` library and the `pytube` package. It allows you to enter the URL of a YouTube video and download it to your local machine.

## Installation

To use this application, you need to have Python installed on your system. You can download Python from the official website: [Python.org](https://www.python.org/).

You also need to install the `pytube` package. You can install it using pip:

```
pip install pytube
```

## Usage

1. Run the script in Python.
2. A window will open with the title "YouTube Video Downloader Application".
3. Enter the URL of the YouTube video you want to download in the text field.
4. Click the "Download Video" button.
5. The application will display the status of the download process.
6. Once the video is downloaded, the application will show a success message.

**Note:** Make sure you enter a valid YouTube video URL. If an incorrect link is entered, the application will display an error message.

## Example

```python
from tkinter import *
from pytube import YouTube

root = Tk()
root.geometry("400x250")
root.title("YouTube Video Downloader Application")

def download():
    try:
        myVar.set("Downloading...")
        root.update()
        YouTube(link.get()).stream.first().download()
        link.set("Video downloaded successfully")
    except Exception as e:
        myVar.set("Mistake")
        root.update()
        link.set("Enter correct link")

Label(root, text="Welcome to YouTube\nDownload Application", font="Consolas 15 bold").pack()

myVar = StringVar()
myVar.set("Enter the link below")
Entry(root, textvariable=myVar, width=40).pack(pady=10)

link = StringVar()
Entry(root, textvariable=link, width=40).pack(pady=10)

Button(root, text="Download video", command=download).pack()

root.mainloop()
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
