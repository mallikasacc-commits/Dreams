#codeproject
Step 1: Install a C Compiler
First, you need a C compiler on your computer to transform the source code into an executable program.
 * On Windows: The most common way is to install MinGW-w64. You can download it from the official MinGW-w64 website. This provides a GCC compiler that runs on Windows.
 * On macOS: Install Xcode Command Line Tools by opening the Terminal and running xcode-select --install. This will give you the Clang compiler.
 * On Linux: Most Linux distributions come with the GNU Compiler Collection (GCC) pre-installed. You can verify this by typing gcc --version in your terminal. If it's not installed, you can get it using your package manager (e.g., sudo apt-get install build-essential for Debian/Ubuntu).
Step 2: Prepare Your Files
 * Save the Code: Copy the C code into a plain text file and save it as texture_segmentation.c.
 * Create the Input Directory: The code is set to read an image from the path C:\texture_segmentation\. You need to create this directory on your computer.
 * Find a RAW Image: The code is specifically designed to work with 8-bit grayscale RAW images with a size of 256x256 pixels.
   * Find a grayscale image you want to test with.
   * Use an image editing tool (like GIMP, ImageJ, or a Python script with Pillow/OpenCV) to resize it to 256x256 pixels and save it as a RAW grayscale file. Make sure it's saved without any headers. This is a common format in image processing for direct pixel data access.
   * Rename this file to raw.png and place it in the C:\texture_segmentation\ directory you created. Even though the file extension is .png in the code, the fopen call with "rb" (read binary) will treat it as a raw binary file.
Step 3: Compile and Run from the Command Line
 * Open a Terminal:
   * Windows: Open Command Prompt or PowerShell.
   * macOS/Linux: Open Terminal.
 * Navigate to the Code's Directory: Use the cd command to change your current directory to where you saved texture_segmentation.c. For example: cd path/to/your/code.
 * Compile the Code: Use your C compiler to compile the source file. You need to link the math library using the -lm flag.
   * gcc texture_segmentation.c -o texture_segmentation -lm
   * This command will create an executable file named texture_segmentation.
 * Run the Executable:
   * ./texture_segmentation
   * When you run it, the program will process the raw.png file.
   * The output will be a new file named cluster2.raw saved in the same C:\texture_segmentation\ directory.
Step 4: View the Output
The output file cluster2.raw is also a raw binary file. To view the segmented image, you can use the same image editing tools you used to create the input file.
 * Open your image editor and choose to open a RAW file.
 * Specify the dimensions as 256x256, select 8-bit grayscale, and ensure there is no header.
 * The segmented image should be displayed, showing the original image partitioned into different clusters based on their texture properties.
