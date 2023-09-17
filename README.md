# 使用分割遮罩进行基于 GAN 的图像合成
![teaser](docs/assets/teaser.png)

> [**使用分割遮罩进行基于 GAN 的图像合成**]



抽象无缝混合来自多个图像的特征极具挑战性，因为照明、几何和部分遮挡的复杂关系会导致图像不同部分之间的耦合。尽管最近关于GANs的工作能够合成逼真的头发或面部，但仍然很难将它们组合成一个单一的，连贯的，合理的图像，而不是一组脱节的图像补丁。我们提出了一种基于GAN反转的图像混合的新解决方案，特别是针对发型转移问题。我们提出了一种新的图像混合潜在空间，该空间在保留细节和编码空间信息方面更好，并提出了一种新的GAN嵌入算法，该算法能够稍微修改图像以符合通用分割掩码。我们的新颖表示能够从多个参考图像中转移视觉属性，包括痣和皱纹等特定细节，并且由于我们在潜在空间中进行图像混合，因此我们能够合成连贯的图像。我们的方法避免了混合其他方法中存在的伪影，并找到了全局一致的图像。我们的结果表明，在用户研究中，与当前技术水平相比，我们有了显着改进，用户在95%以上的时间内更喜欢我们的混合解决方案。


## 安装
- 克隆存储库：:
``` 
git clone https://github.com/ZPdesu/Barbershop.git
cd Barbershop
```
- 依赖关系:  
我们建议使用 Anaconda 运行此存储库。 中提供了用于定义环境的所有依赖关系。`environment/environment.yaml`.


## 下载 II2S 映像
Please download the [II2S](https://drive.google.com/drive/folders/15jsR9yy_pfDHiS9aE3HcYDgwtBbAneId?usp=sharing) 
and put them in the `input/face` folder.


## 开始  
预处理您自己的图像。请将原始图像放入文件夹中。`unprocessed` folder.
```
python align_face.py
```

产生现实的结果：:
```
python main.py --im_path1 90.png --im_path2 15.png --im_path3 117.png --sign realistic --smooth 5
```

产生忠实于面膜的结果：:
```
python main.py --im_path1 90.png --im_path2 15.png --im_path3 117.png --sign fidelity --smooth 5
```



## Todo List
* 添加详细的自述文件
* 更新蒙版修复代码
* 集成图像编码器
* 添加预处理步骤
* ...

## 确认
此代码大量借鉴了 [II2S](https://github.com/ZPdesu/II2S).

