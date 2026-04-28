# Ex01-Image Handling and Pixel Transformations Using OpenCV

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name:** GANESH D  
- **Register Number:** 212223240035

### Ex. No. 01


## Step 1: Import python necessary libraries and Read the image using CV2
```
import cv2
import matplotlib.pyplot as plt

img = cv2.imread('Eagle_in_Flight.jpg', cv2.IMREAD_COLOR
```

## Step 2: Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order) and display the image
```
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```

<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/3633842d-9f2f-491c-87e4-61bc8380fb19" />


## Step 3: Print image size
```
img_rgb.shape
```

<img width="370" height="61" alt="image" src="https://github.com/user-attachments/assets/e947d886-1571-48d4-bf4f-9a1894764806" />

## Step 4: Draw Line top left to bottom right(diagonal line)
```
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)

plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```

<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/b3bb7296-7474-4a2c-b0f1-2b5a2a954d2b" />

## Step 5: Draw Circle on eagle image
```
# Load the image
image = cv2.imread('Eagle_in_Flight.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

circle_img = cv2.circle(img_rgb,(400,300),150,(0,255,0),10) # cv2.circle(image, center, radius, color, thickness)

plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```

<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/38f27525-374d-4b03-92b1-3e0e9ad9439d" />


## Step 6: Draw Rectangle to fit te outline of image
```
# Load the image
image = cv2.imread('Eagle_in_Flight.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)

plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```

<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/51642393-1861-43bc-b74b-1e81d4a2ed5e" />


## Step 7: Add Text On Image
```
# Load the image
image = cv2.imread('Eagle_in_Flight.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 40), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 2, cv2.LINE_AA)

plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```

<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/5826f2a5-b970-4406-9f49-bf9da5e9bfd3" />

## Step 8: Load the image and convert to RGB image
```
# Load the image
image = cv2.imread('Eagle_in_Flight.jpg')

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```

<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/c6b0c0c4-5b0f-4889-b453-22ea41859d80" />

## Step 9: Convert RGB to HSV
```
# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)

# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```

<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/3c06afa4-01a1-4e2f-956a-ba0f6a8b420b" />


## Step 10: Convert RGB to Gray
```
# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)

# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```

<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/047bd31d-107c-4e73-a912-1968295fc2ad" />


## Step 11: Convert RGB to YCrCb
```
# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)

# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```

<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/5d830df5-e969-4ede-b137-e59671d5d3b2" />

## Step 13: Convert HSV back to RGB
```
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)

plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```

<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/348e5ef4-4ce9-4e74-bcc6-be86c4ab93dd" />


## Step 14: White Block
```
# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499

# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```

<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/8199e4cc-7eb9-4e51-bf52-81a0734e3ca0" />


## Step 15: Resize Of Image
```
image = cv2.imread('Eagle_in_Flight.jpg')
image.shape
```
<img width="410" height="73" alt="image" src="https://github.com/user-attachments/assets/24678184-6c4c-48ce-81b8-f9276f04544b" />

```
# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)

# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)

resized_image_rgb.shape
```
<img width="320" height="65" alt="image" src="https://github.com/user-attachments/assets/679327c5-c5b7-435b-bbad-642da1b527a1" />

```
# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```
<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/c289d956-8e0c-4516-9bf4-fc788d9399e2" />


## Step 16: Crop
```
image = cv2.imread('Eagle_in_Flight.jpg')

# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349

# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)

# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show() 
```

<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/c717833d-41e2-4f29-8846-11e7c7a7d39a" />


## Step 17: Horizontal Flip
```
image = cv2.imread('Eagle_in_Flight.jpg')

# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)

# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)

# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```

<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/ea21169d-274f-4523-a0d6-54141fbb1112" />


## Step 18: Vertical Flip
```
# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)

# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)

# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```
<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/c906f2d3-44a4-45f3-9198-5205d8d8bdd1" />


## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

