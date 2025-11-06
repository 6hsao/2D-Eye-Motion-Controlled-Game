**Technical Configuration & Specifications**

**Engine Compatibility**
*   The primary development and testing environment for this project is **Unreal Engine 5.2**.
*   Compatibility with **Unreal Engine 4.27** is also provided. Please use the corresponding tagged version in the project repository.

**Core Plugins & Dependencies**
*   The game's functionality relies on the integrated **OpenCVForUnreal plugin**, which handles all image processing and recognition tasks.
*   Upon opening the project for the first time, navigate to **Edit -> Plugins** in the editor. Locate and **enable** this OpenCV plugin under the Project section, then restart the editor.

**Game Runtime Configuration**
*   **Camera**: A connected, functioning camera is required (1080p resolution or higher is recommended). Ensure that camera access permissions are granted to the game/editor in your system settings.
*   **Lighting**: For optimal recognition performance, please play in a well-lit and evenly lit environment.
*   **Calibration**: On first run, it is essential to complete the in-game **eye movement calibration** process to enhance control accuracy.

**Performance & Architecture**
*   The project utilizes **UE4's multi-threaded FRunnable** and **asynchronous calling** technologies to handle image recognition tasks. This ensures the smooth operation of the game's main thread without stuttering caused by recognition computations.

**Core Recognition Technology**
*   Employs a **DNN (Deep Neural Network)** for real-time face detection, eye tracking, and facial action analysis.
*   We have conducted comparisons of various recognition models, allowing for the selection of a model that best balances accuracy and performance based on specific needs.

**Image Processing Pipeline**
*   Implements efficient conversion from the camera feed (OpenCV `Mat`) to the game texture (`UTexture2D`).
*   Supports essential image processing functions, such as frame cropping and dynamic brightness/contrast adjustment, to optimize recognition effectiveness under varying lighting conditions.

**Model Preparation (Important)**
*   **Pre-trained model files must be manually downloaded before use.**
*   **Download Source**: Obtain the required model files from:
    `https://github.com/spmallick/learnopencv/tree/master/FaceDetectionComparison/models`
*   **Target Directory**: Place the downloaded model files into the following directory within your project:
    `YourProjectRoot\Plugins\OpenCVForUnreal-5.2\OpenCVForUnreal\Config`
