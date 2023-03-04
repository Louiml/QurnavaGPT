# QurnavaGPT - Stupid AI
QurnavaGPT is an AI language model that is being developed using C++. The ultimate goal of this project is to create a powerful and sophisticated AI that can understand natural language and generate human-like responses in real-time.

To achieve this, QurnavaGPT will use advanced machine learning algorithms and neural network architectures to learn from large datasets of text, enabling it to identify patterns and generate responses that are relevant and coherent. The model will be trained on a wide range of data, including books, articles, websites, and social media posts, among others.

In its current state, QurnavaGPT is still in development and not yet a fully functional GPT. However, once completed, it has the potential to revolutionize the way we interact with computers and other digital devices. With QurnavaGPT, it may be possible to carry on natural, human-like conversations with computers, making it easier to access information and complete complex tasks.

# Install g++ compiler

1. Download and install the MinGW-w64 compiler toolchain from https://sourceforge.net/projects/mingw-w64/. Make sure to select the correct architecture for your system (32-bit or 64-bit).
2. Add the bin directory of the MinGW-w64 installation to your system's PATH environment variable. For example, if you installed MinGW-w64 in C:\mingw-w64, you should add C:\mingw-w64\bin to the PATH variable.

# Install Boost library

1. Download the Boost library from https://www.boost.org/users/download/.
2. Extract the downloaded file to a directory of your choice, for example, C:\boost.
3. Open a command prompt and navigate to the directory where you extracted Boost.
4. Run the following command to build the Boost library:

```
.\bootstrap.bat
```

1. After the bootstrapping process is completed, run the following command to build the Boost libraries:

```
.\b2.exe
```

1. This process may take a while depending on your system's configuration. Once the build is completed, you should see the Boost libraries in the stage\lib directory.

# Create a new C++ project in Visual Studio Code

1. Open Visual Studio Code and create a new folder for your project.
2. Open the folder in Visual Studio Code and create a new file named main.cpp.
3. Add the following code to `main.cpp`:

```cpp
#include <iostream>
#include <string>
#include <boost/asio.hpp>

using boost::asio::ip::tcp;

int main(int argc, char** argv)
{
    if (argc > 1 && std::string(argv[1]) == "hey") {
        std::cout << "Hey, how can I help you?" << std::endl;
        if (argc > 2 && std::string(argv[2]) == "may i ask you a question?") {
            std::cout << "Just ask!" << std::endl;
        } else if (argc > 2 && std::string(argv[2]) == "how are you?") {
            std::cout << "Bad cause the one who are made me work on other projects." << std::endl;
        }
    } else if (argc == 1) {
        std::cout << "Please put a question." << std::endl;
    } else if (argc > 1 && std::string(argv[1]) == "ip") {
            try {
                boost::asio::io_service io_service;
                tcp::resolver resolver(io_service);
                tcp::resolver::query query(boost::asio::ip::host_name(), "");
                tcp::resolver::iterator iter = resolver.resolve(query);
                tcp::resolver::iterator end;

                while (iter != end) {
                    tcp::endpoint ep = *iter++;
                    std::cout << "Your IP address is: " << ep.address().to_string() << std::endl;
                }
            }
            catch (std::exception& e) {
                std::cerr << "Exception: " << e.what() << std::endl;
            }
        } else {
        std::cout << "As an AI language model, I do not generate " + std::string(argv[1]) + " in the traditional sense.\nHowever, if there is an issue with my functioning, I may provide feedback or prompts to help\nresolve the problem. For example, if I do not understand a question or input, I may ask\nfor clarification or suggest alternative phrasing. Similarly, if I encounter a technical issue, I may\nprovide information or instructions to address the problem." << std::endl;
    }
    return 0;
}
```
This code creates an "AI" I can't even call that an AI **yet**

1. Open a terminal in Visual Studio Code by pressing Ctrl+Shift+ (backtick) or selecting Terminal > New Terminal from the menu.
2. Type `g++ main.cpp -o main.exe -lws2_32 -I path/to/boost/headers -L path/to/boost/libraries`
