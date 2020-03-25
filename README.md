When we download/upload something from a cloud server, it gives more transfer rate as compared to a normal server. We can use Google Drive for storage as well as fast speed download. The problem is how to upload something to G-Drive direct from Internet. So, Here we will see a solution to upload anything to Google drive directly from Internet.

All we need is google account and a few lines of code.

[Colab Google](https://colab.research.google.com/notebooks/intro.ipynb)

Google Colab is a free cloud service with GPU support. It is like Jupyter Notebook and very simple to use. In this tutorial, we will be using Google Colab to download anything to our google drive.

**Step #1 : Sign in to Google Colab and Create a new Python3 notebook.**
![Atom](https://i.imgur.com/8Qu5ivW.png)

![Atom](https://i.imgur.com/QZzfIiJ.png)

**Step #2 : Importing google drive to colab**

To import google drive, write this code in code section of colab and run it by `Ctrl+Enter` .

```
from google.colab import drive
drive.mount( '/content/gdrive' )
```

![Atom](https://i.imgur.com/vyNxcAO.png)

![Atom](https://i.imgur.com/ZVmz6jR.png)

On running code, one blue link and a text box will appear we need to provide a permission text. So click the link and a new tab will open where you will be asked for permission to access google drive. After providing permissions a text will be displayed that we need to Copy and paste on colabs text box.

![Atom](https://i.imgur.com/yZbWnSh.png)

Paste text in box and press enter. That all to import gdrive. We can see google drive on Left side Panel.

![Atom](https://i.imgur.com/whlXOFZ.png)

**Step #3 : Download something to Google Drive**

To download something all we need is URL to downloadable file.

```
import requests
file_url = "http://1.droppdf.com/files/5iHzx/automate-the-boring-stuff-with-python-2015-.pdf"
r = requests.get(file_url, stream = True)
with open("/content/gdrive/My Drive/python.pdf","wb") as file:
  for block in r.iter_content(chunk_size = 1024):
    if block:
      file.write(block)
```

![Atom](https://i.imgur.com/KQGMrKI.png)

We can see on the left side panel that pdf file is downloaded.

**Conclusion:**

We can use google colab to download any file on google drive.

As you can see a folder parrot (parrot OS of 3.7 GB ), downloaded to gdrive using Colab.

Material source:Geeks for Geeks
