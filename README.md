# COLOR_CONVERSIONS_OF-IMAGE
## AIM
Write a Python program using OpenCV that performs the following tasks:

i) Read and Display an Image.

ii) 	Draw Shapes and Add Text.

iii) Image Color Conversion.

iv) Access and Manipulate Image Pixels.

v) Image Resizing

vi) Image Cropping

vii) Image Flipping

viii)	Write and Save the Modified Image


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Load an image from your local directory and display it.
### Step2:
o	Draw a line from the top-left to the bottom-right of the image.
o	Draw a circle at the center of the image.
o	Draw a rectangle around a specific region of interest in the image.
o	Add the text "OpenCV Drawing" at the top-left corner of the image.

### Step3:
o	Convert the image from RGB to HSV and display it.
o	Convert the image from RGB to GRAY and display it.
o	Convert the image from RGB to YCrCb and display it.
o	Convert the HSV image back to RGB and display it.

### Step4:
o	Access and print the value of the pixel at coordinates (100, 100).
o	Modify the color of the pixel at (200, 200) to white.

### Step5:
o	Resize the original image to half its size and display it.
### Step6:
o	Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
### Step7:
o	Flip the original image horizontally and display it.
o	Flip the original image vertically and display it.

### Step8:
o	Save the final modified image to your local directory.


##### Program:
### Developed By: SUBISHESH P
### Register Number: 21222324

### i)Read and Display an Image
```
# Step 1: Load an image from your local directory and display it
import cv2
image_path = 'elephant.jpg'  # Replace with your image path
image = cv2.imread(image_path)

# Check if the image was loaded successfully
if image is None:
    print("Error: Could not read the image.")
else:
    cv2.imshow('Original Image', image)
    cv2.waitKey(0)
```
### OUTPUT:
![Screenshot 2024-09-04 232233](https://github.com/user-attachments/assets/7d353a72-f464-4055-8291-e81e816513f2)

### ii)Draw Shapes and Add Text
```
# Step 2: Draw Shapes and Add Text
# Draw a line from the top-left to the bottom-right
start_point = (0, 0)
end_point = (image.shape[1], image.shape[0])
line_color = (255, 0, 0)  # Blue color in BGR
thickness = 2
image_with_line = cv2.line(image.copy(), start_point, end_point, line_color, thickness)

# Draw a circle at the center of the image
center_coordinates = (image.shape[1] // 2, image.shape[0] // 2)
radius = 50
circle_color = (0, 255, 0)  # Green color in BGR
thickness = 3
image_with_circle = cv2.circle(image_with_line, center_coordinates, radius, circle_color, thickness)

# Draw a rectangle around a specific region of interest
top_left = (50, 50)
bottom_right = (200, 200)
rectangle_color = (0, 0, 255)  # Red color in BGR
thickness = 2
image_with_rectangle = cv2.rectangle(image_with_circle, top_left, bottom_right, rectangle_color, thickness)

# Add text to the image
text = "OpenCV Drawing"
org = (10, 30)  # top-left corner of the text string
font = cv2.FONT_HERSHEY_SIMPLEX
font_scale = 1
text_color = (255, 255, 255)  # White color
thickness = 2
image_with_text = cv2.putText(image_with_rectangle, text, org, font, font_scale, text_color, thickness, cv2.LINE_AA)

cv2.imshow('Image with Shapes and Text', image_with_text)
cv2.waitKey(0)
```
### OUTPUT:
![Screenshot 2024-09-04 232259](https://github.com/user-attachments/assets/42fc35d5-bbfa-4b2b-aa11-e8f6079b7e17)

### iii)Image Color Conversion
```
# Step 3: Image Color Conversion
# Convert the image from RGB to HSV and display it
hsv_image = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
cv2.imshow('HSV Image', hsv_image)
cv2.waitKey(0)

# Convert the image from RGB to GRAY and display it
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
cv2.imshow('Gray Image', gray_image)
cv2.waitKey(0)

# Convert the image from RGB to YCrCb and display it
ycrcb_image = cv2.cvtColor(image, cv2.COLOR_BGR2YCrCb)
cv2.imshow('YCrCb Image', ycrcb_image)
cv2.waitKey(0)

# Convert the HSV image back to RGB and display it
hsv_to_rgb_image = cv2.cvtColor(hsv_image, cv2.COLOR_HSV2BGR)
cv2.imshow('HSV to RGB Image', hsv_to_rgb_image)
cv2.waitKey(0)
```
### OUTPUT:
# Convert the image from RGB to HSV and display it:
![Screenshot 2024-09-04 232323](https://github.com/user-attachments/assets/aab3958b-88f3-4190-a540-740e2dc919ee)

# Convert the image from RGB to GRAY and display it:
![Screenshot 2024-09-04 232333](https://github.com/user-attachments/assets/59de50b4-3323-4777-a980-4e68766145af)

# Convert the image from RGB to YCrCb and display it:
![Screenshot 2024-09-04 232344](https://github.com/user-attachments/assets/28dd716e-92c4-4ce7-afdc-71e1679e07d8)

# Convert the HSV image back to RGB and display it:
![Screenshot 2024-09-04 232354](https://github.com/user-attachments/assets/f93f34bd-a658-4926-8cf0-2fe6ed4d7d52)

### iv)Access and Manipulate Image Pixels
```
# Step 4: Access and Manipulate Image Pixels
# Access and print the value of the pixel at coordinates (100, 100)
pixel_value = image[100, 100]
print(f"Pixel value at (100, 100): {pixel_value}")

# Modify the color of the pixel at (200, 200) to white
image[200, 200] = [255, 255, 255]
print(f"Modified pixel value at (200, 200): {image[200, 200]}")
```
### OUTPUT:
![Screenshot 2024-09-04 232425](https://github.com/user-attachments/assets/69e2a23d-ad62-414d-8f80-cbe2e88ca57e)

### v)Image Resizing
```
# Step 5: Image Resizing
# Resize the original image to half its size and display it
resized_image = cv2.resize(image, (image.shape[1] // 2, image.shape[0] // 2))
cv2.imshow('Resized Image', resized_image)
cv2.waitKey(0)
```
### OUTPUT:
![Screenshot 2024-09-04 232448](https://github.com/user-attachments/assets/7c5963e1-6b58-47f9-8cfb-276012270802)

### vi)Image Cropping
```
# Step 6: Image Cropping
# Crop a region of interest (100x100 pixels starting at (50, 50)) and display it
roi = image[50:150, 50:150]
cv2.imshow('Cropped ROI Image', roi)
cv2.waitKey(0)
```
### OUTPUT:
![Screenshot 2024-09-04 232512](https://github.com/user-attachments/assets/d8f76ed5-c9f3-4ac4-a4b4-fabb376c07a1)

### vii)Image Flipping
```
# Step 7: Image Flipping
# Flip the original image horizontally and display it
flipped_horizontally = cv2.flip(image, 1)
cv2.imshow('Horizontally Flipped Image', flipped_horizontally)
cv2.waitKey(0)

# Flip the original image vertically and display it
flipped_vertically = cv2.flip(image, 0)
cv2.imshow('Vertically Flipped Image', flipped_vertically)
cv2.waitKey(0)
```
### OUTPUT:
# Flip the original image horizontally and display it:
![Screenshot 2024-09-04 232535](https://github.com/user-attachments/assets/fb700999-dd6e-4ea3-82a6-8c72f396ee3f)

# Flip the original image vertically and display it:
![Screenshot 2024-09-04 232600](https://github.com/user-attachments/assets/e938577d-fdb0-46e5-a920-df5b55f7feb7)

### viii)Write and Save the Modified Image
```
# Step 8: Write and Save the Modified Image
output_path = 'output.jpg'
cv2.imwrite(output_path, image_with_text)
print(f"Modified image saved as {output_path}")
```
### OUTPUT:
![Screenshot 2024-09-04 234327](https://github.com/user-attachments/assets/33e7eb87-7960-4eab-accb-44e60633f430)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed  successfully using the python program.







