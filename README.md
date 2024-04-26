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
    * **TODO :** obj材质系统导入
    * **TODO :** gltf模型及材质支持

* 基础模型摆件 :
    * 动态生成矩形、平面、方块
    * **TODO :** 
    * 球 
    * 可编辑网格

* Shaders :
    * Init/loading/binding from anywhere
    * G-Buffer support
    * PBR material pipeline compliant
	* **TODO :** UBOs

* Skybox :
    * 6-faced cubemap based
    * Screenquad based
    * Equirectangular/spherical maps
    * HDR
    * Deferred Rendering compliant
    
* Resources Manager :
    * **TODO :** Resources (textures, shaders, models, materials...) centralization

* Lights :
    * Point light
    * Directional light
    * **TODO :** Spot light

* Lighting :
    * Cook-Torrance BRDF
    * Deferred Rendering
    * **TODO :** Shadow-mapping (PCF/Variance)
    * **TODO :** Tiled Deferred Rendering (Compute shaders ?)

* PBR Pipeline :
    * BRDF :
        * Cook-Torrance model
        * Diffuse : Lambertian/Disney
        * Fresnel term : Schlick
        * Microfacet distribution : GGX
        * Geometry attenuation : GGX-Smith
    * Material pipeline using a roughness/metalness workflow
    * Image-Based Lighting (Epic split-sum method) :
        * Diffuse irradiance
        * Specular radiance

* Post-processing :
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
