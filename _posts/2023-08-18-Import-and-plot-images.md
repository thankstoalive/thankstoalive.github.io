---
title: 이미지 가져오기 및 출력하기
date: 2023-08-20
categories: [Image, Basic]
tags: [python, image]     # TAG names should always be lowercase
---

# 개요
- 파이썬에서 이미지를 처리하는 대표적인 라이브러리는 PIL과 cv2가 있음
-  PIL은 Python Imaging Library의 약자로, 이미지를 다루기 위한 다양한 기능을 제공
-  cv2는 openCV의 파이썬 바인딩으로, 컴퓨터 비전과 관련된 고급 이미지 처리 기능을 제공

# 특징
- `(height, width, channel)` 모양의 이미지 데이터 생성
- PIL은 이미지를 RBG 채널 순서로 읽고, openCV는 BGR 채널 순서로 읽음


# PIL 방법: 코드 및 결과

```python
from PIL import Image
import numpy as np
import matplotlib.pyplot as plt

# Load image
img = Image.open(img_path)
img_array = np.array(img)

# Plot image
plt.imshow(img_array)
plt.title(f'PIL, {img_array.shape}')
```

![img](/images/PIL-lena.png)

# OpenCV 방법: 코드 및 결과

```python
import cv2
import matplotlib.pyplot as plt

# Load image
img = cv2.imread(img_path)
img_RGB = cv2.cvtColor(img, cv2.COLOR_BGR2RGB) # BGR 채널을 RGB 채널로 변경

# Plot image
plt.imshow(img_RGB)
plt.title(f'cv2, {img_RGB.shape}')
```

![img](/images/cv2-lena.png)

