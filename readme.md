# Microcontrollers Testing Suite

The **Microcontrollers Testing Suite** is a testing environment for embedded systems and microcontrollers. This suite allows you to run, manage, and monitor different threads and tasks, ensuring your microcontroller firmware operates correctly and efficiently.


## Getting Started


### How to Include the Suite in Your Project

1. **Add to your build system**:  
   Include the testing suite source files in your `CMakeLists.txt` or `Makefile`.

   For example, if you are using **CMake**, add the following to your `CMakeLists.txt`:

   ```cmake
   add_subdirectory(MicrocontrollersTestingSuite)
   ```

   If you are using **Make**, update your makefile accordingly:

   ```make
   SRCS += MicrocontrollersTestingSuite/src/*
   ```

2. **Include the header file**:  
   Add the following line in your code where the testing suite is required:

   ```c
   #include "threads_inc.h"
   ```

3. **Start the main thread**:  
   You will need to initialize and run the main thread in your project using the following snippet:

   ```c
   osThreadDef(MainThread, mainThread, osPriorityNormal, 0, 1024);
   defaultTaskHandle = osThreadCreate(osThread(MainThread), NULL);
   ```

### HAL Integration

By default, this testing suite is designed to work with the **HAL** libraries. However, if you are using a custom HAL or need to modify certain parts of the code to match your environment, you can easily customize it.

All areas that may need to be edited for custom HAL support are marked with:

```c
//@Edit
```

Simply search for `//@Edit` within the code and make the necessary changes to adapt to your custom HAL setup.


## Contribution

If you encounter any bugs or have suggestions for new features, feel free to contribute by opening an issue or submitting a pull request on our GitHub repository.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Enjoy using the **Microcontrollers Testing Suite** for robust and reliable firmware development!