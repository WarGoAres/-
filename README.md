# -
#參考書數位影像處理全華張元翔
影像處理.py
import cv2
import numpy as np
import matplotlib.pyplot as plt



#gamma correction

def gamma_correction(img,c=1,gamma=2.2):
    result = img.copy()
    
    result = (1/c * result) ** (1/gamma)
    result *= 255
    result = np.clip(result, 0, 255)
    result = result.astype(np.uint8)
    
    return result

# Read image
img_path = r"C:\Users\kang\OneDrive\桌面\新增資料夾 (4)\下載.png"#路徑要貼自己的路徑
img = cv2.imread(img_path)

# Gamma correction
result = gamma_correction(img)

# Display original and corrected images
cv2.imshow("Original Image", img)
cv2.imshow("Gamma Corrected Image", result)
cv2.waitKey(0)
cv2.destroyAllWindows()

