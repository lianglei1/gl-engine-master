GLEngine
======
GLEngine 是一个 C++ OpenGL PBR图形渲染引擎，旨在展示各种3D图形技术。该项目clone自：gl-engine https://github.com/JoshuaSenouf/gl-engine 原作者不再更新，本项目将完成原作者todo项功能并优化扩展其功能使其可用于商用。

原项目demo视频地址 : https://vimeo.com/200574427


Screenshots
------

* Example using Image-Based Lighting :

![](https://image.ibb.co/nt76La/Screenshot_from_2017_02_23_13_26_44.png)
* G-Buffer structure :

![](http://image.noelshack.com/fichiers/2016/52/1483180466-glengine2.png)


功能：
------

* 相机 :
    * 运动
    * 推进、远离
    * 曝光模式 :
        * 孔径
        * 快门速度
        * ISO
    * **TODO :** 
    * 景深
    * 泛光（Bloom）
    * 相机耀斑（CameraLensEffects）

* 纹理 :
    * 纹理对象
	* 各向异性滤波
    * HDR
    * Cubemap

* 材质 :
	* PBR材质管线 :
		* 反照率（Albedo）
        * 法相（Normal）
		* 粗糙度（Roughness）
		* 金属度（Metalness）
		* 环境光遮蔽（AO）
	* **TODO :** 优化延迟渲染 G-Buffer

* 3D模型/网格 :
    * obj文件格式支持
    * **TODO :** 
    * obj材质系统导入
    * Gltf模型及材质支持

* 基础模型摆件 :
    * 动态生成矩形、平面、方块
    * **TODO :** 
    * 球 
    * 可编辑网格

* 着色器 :
    * 材质对象
    * 延迟渲染
    * PBR光照管线
	* **TODO :** Uniform 块支持

* 天空盒 :
    * 六面体天空
      
    
* 资源管理器  :
    * **TODO :**资源全局管理优化(textures, shaders, models, materials...) 

* 灯光 :
    * 点光源
    * 太阳光
    * **TODO :** 
    * 聚光灯
    * 矩形光源

* 光照 :
    * Cook-Torrance BRDF
    * 延迟渲染
    * **TODO :** 硬阴影、软阴影 Shadow-mapping (PCF/Variance)
    * **TODO :** 延迟渲染优化

* PBR 管线 :
    * BRDF :
        * Cook-Torrance model
        * Diffuse : Lambertian/Disney
        * Fresnel term : Schlick
        * Microfacet distribution : GGX
        * Geometry attenuation : GGX-Smith
    * 材质贴图规范按照金属度粗糙度工作流程
    * 基于图像光照Image-Based Lighting (Epic split-sum method) :
        * Diffuse irradiance
        * Specular radiance

* 视频特效 Post-processing :
    * Scalable Ambient Obscurance (SAO)
    * FXAA
    * Motion Blur (camera/per-fragment)
    * Tonemapping (Reinhard, Filmic, Uncharted)
	* **TODO :** Bloom
	* **TODO :** Depth of Field
	* **TODO :** Screen-Space Reflections
	* **TODO :** Lens Flare
	* **TODO :** Eye Adaptation
 
* Utility :
    * GUI using ImGui
    * Basic/naive GPU profiling
    * G-Buffer visualization for debugging purpose
	* Borderless Fullscreen
    * **TODO :** Logging
    * **TODO :** CPU profiling
    * **TODO :** G-Buffer export as .png
    * **TODO :** GUI using Qt5 (which imply a whole project revamping)

How to use
------
GLEngine was written using Linux, QtCreator as the IDE, CMake 3.0+ as the building tool, OpenGL 4.0+ as the Graphics API and a C++11 compiler in mind.

Download the source, open the CMakeList.txt file with QtCreator, build the project, and everything should be ready to use.

* In GLEngine :
    * Hold the right mouse button to use the camera and its features
    * Toggle between the different buffers using the 1-9 buttons

Dependencies (included)
------
- Window & Input system : GLFW
- OpenGL Function Loader : GLAD
- OpenGL Mathematic Functions : GLM
- Image Loading : stb
- Mesh Loading : Assimp

Credits
------
- Joey de Vries (LearnOpenGL)
- Kevin Fung (Glitter)
