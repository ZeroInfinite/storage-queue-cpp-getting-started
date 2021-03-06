---
services: storage
platforms: cpp
author: pcibraro
---

# Azure Storage Service Samples in C++

Demonstrates how to use the Queue Service.

- Azure Queue storage provides cloud messaging between application components. In designing applications for scale, application components are often decoupled, so that they can scale independently. Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device. Queue storage also supports managing asynchronous tasks and building process work flows. This sample demonstrates how to perform common tasks including inserting, peeking, getting and deleting queue messages, as well as creating and deleting queues.

Note: This sample uses the Windows Azure Storage client library for C++ available through a Nuget package, which depends on the Visual Studio version you will use for development. For Visual Studio 2015, use the Nuget package "wastorage.v140". For Visual Studio 2013, use "wastorage.v120".

If you don't have a Microsoft Azure subscription you can get a FREE trial account [here](http://go.microsoft.com/fwlink/?LinkId=330212).

## Running this sample in Windows

This sample can be run using either the Azure Storage Emulator that installs as part of the Windows Azure SDK - or by updating the storage_connection_string variable defined at the top of the program.

To run the sample using the Storage Emulator (Windows Azure SDK):

1. Download and Install the Azure Storage Emulator [here](http://azure.microsoft.com/en-us/downloads/).
2. Start the Azure Storage Emulator (once only) by pressing the Start button or the Windows key and searching for it by typing "Azure Storage Emulator". Select it from the list of applications to start it.
3. Set breakpoints and run the project using F10.

To run the sample using the Storage Service

1. Open the storage-queue-getting-started.cpp file and find the variable storage_connection_string. Replace the value (UseDevelopmentStorage=True) with the connection string for the storage service (AccountName=[]...)
2. Create a Storage Account through the Azure Portal and provide your [AccountName] and [AccountKey] in the storage_connection_string variable.
3. Set breakpoints and run the project using F10.

## Running this sample in Linux

In order to compile and run this sample in Linux, you first need to get a local copy of the C++ REST SDK (aka Casablanca) from [here] (https://github.com/Microsoft/cpprestsdk) and the Azure Storage Client Library for C++ from [here] (https://github.com/Azure/azure-storage-cpp). Both libraries must be compiled following the instructions described in the corresponding Github repositories.
Once you have these libraries, follow these instructions to build the samples,

- Clone the project using git:
```bash
git clone https://github.com/Azure-Samples/storage-queue-cpp-getting-started.git
```
The project is cloned to a folder called `storage-queue-cpp-getting-started`. Always use the master branch, which contains the latest release.

- Build the samples:
```bash
cd storage-queue-cpp-getting-started/storage-queue-cpp-getting-started
mkdir build
cd build
CASABLANCA_DIR=<path to Casablanca> AZURESTORAGE_DIR=<path to AzureStorage> CXX=g++-4.8 cmake .. -DCMAKE_BUILD_TYPE=Release
make
```
In the above command, replace `<path to Casablanca>` to point to your local installation of Casablanca and `<path to Casablanca>` to point to your local installation of the Azure Storage Client library. For example, if the file `libcpprest.so` exists at location `~/Github/Casablanca/cpprestsdk/Release/build.release/Binaries/libcpprest.so` and the file `libazurestorage.so` exists at location `~/Github/azure-storage-cpp/Microsoft.WindowsAzure.Storage/build.release/Binaries/libazurestorage.so`, then your `cmake` command should be:
```bash
CASABLANCA_DIR=~/Github/Casablanca/cpprestsdk AZURESTORAGE_DIR=~/Github/azure-storage-cpp CXX=g++-4.8 cmake .. -DCMAKE_BUILD_TYPE=Release
```
The sample is generated under `storage-queue-cpp-getting-started/storage-queue-cpp-getting-started/build/Binaries/`.

## More information
- [What is a Storage Account](http://azure.microsoft.com/en-us/documentation/articles/storage-whatis-account/)
- [How to use Queue Storage from C++](https://azure.microsoft.com/en-us/documentation/articles/storage-c-plus-plus-how-to-use-queues/)
- [Queue Service Concepts](http://msdn.microsoft.com/en-us/library/dd179353.aspx)
- [Queue Service REST API](http://msdn.microsoft.com/en-us/library/dd179363.aspx)
- [Storage Emulator](http://msdn.microsoft.com/en-us/library/azure/hh403989.aspx)
