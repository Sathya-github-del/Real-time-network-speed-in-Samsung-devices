# Real-time-network-speed-in-Samsung-devices
Enable real-time-network-speed in samsung devices

Requirements:
Rooted Samsung phone
- In my case I have rooted Samsung galaxy A04e device
- CS(Common Sense)

 Thanks to [XDA Forums](https://xdaforums.com/t/where-is-the-csc-omc-folder-now-with-cscfeature-xml-file.3795767/) for helping me to locate the cscfeature.xml file.

 Thanks to [XDA Forums](https://xdaforums.com/t/decrypt-decode-note-8-omc-csc-files.3770940/) for helping me to understand how to decode the cscfeature.xml file. 

 Thanks to [GitHub](https://github.com/fei-ke/OmcTextDecoder) for the tool.

 Thanks to [GitHub](https://github.com/fei-ke/OmcTextDecoder/releases) for the jar file.

# Follow the steps

1. **Locate the CSC file**: Find the `cscfeature.xml` file on your Samsung device. In my case, it was found in `Optics/configs/carriers/INS/conf/system/cscfeature.xml`. Copy it to your PC.
2. **Download or Clone this repository**: Download or clone this repository containing the necessary files.
3. **Open Terminal and locate the cloned repo**: Navigate to the directory where you cloned the repository and place the `cscfeature.xml` file there.
4. **Decode CSC file**: Use the following command to decode the cscfeature.xml file:

   java -jar omc-decoder.jar -i cscfeature.xml -o cscfeature_decoded.xml
   
7.**Edit the decoded file**: Open cscfeature_decoded.xml in a text editor like Notepad++ and add the line: 

   <CscFeature_Setting_SupportRealTimeNetworkSpeed>TRUE</CscFeature_Setting_SupportRealTimeNetworkSpeed> 

8. **Encode the file**: Go back to the terminal and use the following command to encode the edited file:
 
   java -jar omc-decoder.jar -e -i cscfeature_decoded.xml -o cscfeature.xml

10. **Replace the CSC file**: Copy the updated cscfeature.xml file and place it in the same folder where you found it originally.

11. **Reboot device**: After replacing the CSC file, reboot your device.

Enable the feature: Go to Settings -> Notifications -> Advance Settings -> Show network speed in real time to enable the feature.



       
