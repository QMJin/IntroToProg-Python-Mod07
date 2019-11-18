# IT FDN 100 A Au 19: Foundations Of Programming: Python
## Assignment 07
**Dev:** *QJin*
**Date:** *11.18.2019*

``` 
# ------------------------------------------------- #
# Title: Lab7-1
# Description: A simple example of storing data in a binary file
# ChangeLog: (Who, When, What)
# <QimingJin>,<11.17.2019>,Created Script
# ------------------------------------------------- #

import pickle  # This imports code from another code file!

# Data -------------------------------------------- #
strFileName = 'AppData.dat'
lstCustomer = []

# Processing -------------------------------------- #
def save_data_to_file(objFile, lstCustomer):
    objFile = open("AppData.dat", "ab")
    pickle.dump(lstCustomer, objFile)
    objFile.close()

def read_data_from_file(objFile):
    objFile = open("AppData.dat", "rb")
    objFileData = pickle.load(objFile)
    objFile.close()
    print(objFileData)

# Presentation ------------------------------------ #
# TODO: Get ID and NAME From user, then store it in a list object
intId = int(input("Enter an Id: "))
strName = str(input("Enter a Name: "))
lstCustomer = [intId, strName]

# TODO: store the list object into a binary file
save_data_to_file(strFileName,lstCustomer)

# TODO: Read the data from the file into a new list object and display the contents
read_data_from_file(strFileName)
