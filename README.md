# Download-Images-Google

Our team was on a project which required us to use images from either old Google slides or Google Docs. However, Google doesn't always make it easy to retrieve those files aside from downloading them locally and then reuploading them up on to the cloud. I helped to write a code with the assistance of ChatGPT to create a way to retrieve image files and automatically uploading it to a folder of your choice.

## Google Docs

* **`function downloadImages() {`**: This line defines a function named downloadImages().

* **`var presentation = SlidesApp.getActivePresentation();`**: This code retrieves the currently active Google Slides presentation using SlidesApp.getActivePresentation() and stores it in the presentation variable.

* **`var slideCount = presentation.getSlides().length;`**: This line counts the number of slides in the presentation and stores the count in the slideCount variable.

* **`var folder = DriveApp.getFolderById("[FOLDER ID]");`**: This code retrieves a Google Drive folder where the downloaded images will be saved. You need to replace [FOLDER ID] with the actual ID of the folder you want to use.

* The script then enters a loop that iterates through each slide in the presentation using for **`(var i = 0; i < slideCount; i++) {`**.

* Inside the loop, it gets the images present on the current slide with **`var images = presentation.getSlides()[i].getImages();`**.

* Another nested loop iterates through the images on the slide using for **`(var j = 0; j < images.length; j++) {`**.

* For each image, it retrieves the image data in the form of a blob with **`var blob = image.getBlob();`**.

* It then creates a file in the specified Google Drive folder using the image blob data with **`var file = folder.createFile(blob);`**.

* Finally, it renames the file using a template that includes the slide number and image number within that slide with **`file.setName(Slide-${i+1}-${j+1}.png);`**. This ensures that each downloaded image has a unique name.




## Google Slides Code Breakdown
* **`function downloadImages() {`**: This line defines a function named downloadImages().

* **`var presentation = SlidesApp.getActivePresentation();`**: This code retrieves the currently active Google Slides presentation using SlidesApp.getActivePresentation() and stores it in the presentation variable.

* **`var slideCount = presentation.getSlides().length;`**: This line counts the number of slides in the presentation and stores the count in the slideCount variable.

* **`var folder = DriveApp.getFolderById("[FOLDER ID]");`**: This code retrieves a Google Drive folder where the downloaded images will be saved. You need to replace [FOLDER ID] with the actual ID of the folder you want to use.

* The script then enters a loop that iterates through each slide in the presentation using for **`(var i = 0; i < slideCount; i++) {`**.

* Inside the loop, it gets the images present on the current slide with **`var images = presentation.getSlides()[i].getImages();`**.

* Another nested loop iterates through the images on the slide using for **`(var j = 0; j < images.length; j++) {`**.

* For each image, it retrieves the image data in the form of a blob with **`var blob = image.getBlob();`**.

* It then creates a file in the specified Google Drive folder using the image blob data with **`var file = folder.createFile(blob);`**.

* Finally, it renames the file using a template that includes the slide number and image number within that slide with **`file.setName(Slide-${i+1}-${j+1}.png)`**;. This ensures that each downloaded image has a unique name.
