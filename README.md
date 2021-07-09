#sharpening
import cv2
#laplaciano
img_in = cv2.imread('data/Fig0338(a)(blurry_moon).tif',0)
from google.colab.patches import cv2_imshow

kernel = np.array([[-1, -1, -1], [-1, 9, -1], [-1, -1, -1]])
img_out = cv2.filter2D(img_in, -1,kernel)

cv2_imshow(img_in)
cv2.waitKey(0)
cv2_imshow(img_out)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Blur the image
gauss = cv2.GaussianBlur(image, (7,7), 0)
# Apply Unsharp masking
unsharp_image = cv2.addWeighted(image, 2, gauss, -1, 0)
