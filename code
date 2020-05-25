import matplotlib.pyplot as plt
import numpy as np

img = np.zeros((6,6,3), np.uint8)
img.fill(255)# 使用白色填充图片区域,默认为黑色

for i in range(6):plt.plot([i,i],[0,5],color='gray')
for j in range(11):plt.plot([0,5],[j,j],color='gray')    
#plt.savefig('ssd_box.png')

f=5
mean=[]

i,j=2,2
cx = (i+0.5)
cy = (j+0.5)

#两个方形box
s_k = 162/60
s_k_plus =213/60
mean.append([cx, cy, s_k, s_k])

s_k_prime = np.sqrt(s_k * s_k_plus)
mean.append([cx, cy, s_k_prime, s_k_prime])


#4个矩形box
for r in [2,3]:  #1,5,6 feature map 2个巨型框，其他四个
    mean.append([cx, cy, s_k * np.sqrt(r), s_k / np.sqrt(r)])
    mean.append([cx, cy, s_k / np.sqrt(r), s_k * np.sqrt(r)])
    

#在图中显示box
for i in range(len(mean)):
    s=mean[i]
    rect = plt.Rectangle((s[0]-0.5*s[2],s[1]-0.5*s[3]),s[2],s[3],fill=False, edgecolor = (i/10,0,0),linewidth=4)
    plt.gca().add_patch(rect)

plt.imshow(img)
plt.axis('off') 
plt.show()
