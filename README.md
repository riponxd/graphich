<h2 align="center">🎮 OpenGL (FreeGLUT) Environment Setup in VS Code</h2>

<p align="center">
This guide explains how to install and configure <b>OpenGL (FreeGLUT)</b> with <b>VS Code</b> on <b>Windows</b>, using <b>MSYS2 (MinGW)</b>.  
Follow the steps carefully to set up a complete graphics development environment.
</p>

---

## 🖥 Operating System
- Windows (64-bit)

---

## 🛠 Required Software & Tools

Download and install the following tools:

1. **Visual Studio Code**  
   👉 https://code.visualstudio.com/download

2. **MSYS2**  
   👉 https://www.msys2.org/

3. **GLAD (OpenGL Loader Generator)**  
   👉 https://glad.dav1d.de/  
   - API: OpenGL  
   - Version: **4.6 (Latest)**  
   - Language: C/C++

---

## 🚀 Installation Steps (Windows)

### 1️⃣ Install VS Code
- Download and install VS Code normally.
- Restart your system if needed.

---

### 2️⃣ Install MSYS2
- Download MSYS2 installer and complete setup.
- After installation, open **MSYS2 MINGW64** terminal.

---

### 3️⃣ Update MSYS2 & Install Required Packages

Run the following commands **one by one**:

```bash
pacman -Syu
pacman -S mingw-w64-ucrt-x86_64-gcc
gcc --version
pacman -S mingw-w64-x86_64-glew
pacman -S mingw-w64-x86_64-glfw
```
Optional: 
```bash
pacman -S mingw-w64-x86_64-freeglut
pacman -S mingw-w64-x86_64-toolchain
```
---

### 4️⃣ Setup Environment Variables
Add System Variable
- Variable Name: `MSYS2`
- Variable Value:
```bash
C:\msys64
```
### Update PATH Variable
Add this path:
```bash
C:\msys64\mingw64\bin
```
> 📌 Restart your system after updating environment variables.

---

### 5️⃣ Generate & Add GLAD
- Generate GLAD files from the website.
- Copy the generated include and src files.
- Paste them inside:
```bash
C:\msys64\mingw64\
```
---

### 6️⃣ Configure VS Code
Install VS Code Extensions
- C/C++
- Run++
- Code Runner

Add Include Path
1. Open *VS Code Settings*
2. Search for `includepath`
3. Add:
```bash
${env:MSYS2}/mingw64/include/
```
---

## 📂 Project Setup
- Download the project ZIP from this repository
- Extract it
- Open the folder in *VS Code*
- Start coding 🎨✨

---

## ✅ Final Check
- `gcc --version` works
- OpenGL headers are detected
- FreeGLUT programs compile without errors

---

## 📌 Notes
- Always run OpenGL-related commands using MSYS2 MINGW64
- Restart VS Code after configuration changes

---
## 📚 Reference
**YouTube video used as learning reference:**
This repository is based on the [OpenGL in Visual Studio Code Bangla ](https://www.youtube.com/watch?v=Bl0tFOpm5RI).

---
<h2 align="center">🚀 OpenGL Run with VS Code Terminal</h2>

<p align="center">
Use the VS Code integrated terminal to compile and run your OpenGL program.
</p>

---

### 1️⃣ Download FreeGLUT

1. Go to the official site:  
👉 Site URL: [FreeGLUT for Windows ➚ ](https://www.transmissionzero.co.uk/software/freeglut-devel/)
 
2. Download:
- **FreeGLUT Windows 32-bit or 64-bit ZIP**  
  (Choose according to your system architecture)

### 📸 Download Page Screenshot

<p align="center">
  <img src="https://i.postimg.cc/rmKyrKs6/Screenshot.png" alt="FreeGLUT Download Page Screenshot" width="800"/>
</p>

---

### 2️⃣ Extract & Verify Folder Structure

Extract the ZIP file.  
For example, extract it to:
```bash
C:\FreeGLUT
```

Your folder structure should look like this:
```bash
C:\FreeGLUT
├── include\GL\glut.h
├── lib\libfreeglut.a
└── bin\freeglut.dll
```
Make sure all files are properly extracted.

---

### 3️⃣ Place the Required DLL File

The `freeglut.dll` file must be available in the same folder where your `.exe` file is created.

For example, if your project output folder is:
```bash
C:\Users\Shahriar Ahammed\Desktop\graphics-design-vscode-environment-setup\Main-Folder
```
Then:

- Copy `C:\FreeGLUT\bin\freeglut.dll`
- Paste it inside the `Main-Folder`

This ensures your program runs without DLL errors.

---

### 4️⃣ Compile & Run the Program

Open **PowerShell** or **Command Prompt** in your project folder and run:

#### 🛠 Compile

```bash
g++ MyProject.cpp -IC:\FreeGLUT\include -LC:\FreeGLUT\lib -lfreeglut -lopengl32 -lglu32 -o MyProject.exe
```

### ▶ Run
```bash
.\MyProject.exe
```

If everything is configured correctly:
- The console may ask for input
- After providing input, the OpenGL window will open successfully 🚀

---

✅ Notes

- Ensure you are using the correct x64 or x86 library based on your system.
- Make sure freeglut.dll exists in the same directory as the executable.
- If you get a missing DLL error, double-check the DLL location.

---
