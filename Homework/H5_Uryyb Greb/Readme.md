# H5_Uryyb Greb
*I missed this class due to sick leave. So I am trying to understand based on Tero's instruction from the homework.*

## Read and summarize

Schneier 2015: Applied Cryptography: 10. Using Algorigthms: 10.1, 10.2, 10.3, 10.4 (from start until the start of "Dereferencing Keys" in 10.4)

### Using Algorithms
    * algorithms are only one small part of security and any system can be compromised if one of the components is weak. It is not enough to just have      strong algorithms, which is other security measures are also important. Cryptography can be used to make petty crime more difficult,but most successful attacks are due to implementation errors, not cryptanalysis. Therefore, it is important to consider all aspects of security when designing a application or system.
    
### 10.1 CHOOSING AN ALGORITHM
  
  - Here has few ways for choosing an algorithm. 
  * Choose a published algorithm, this is pretty good if no one break it yet.
  * Trust a manufacturer by selling equipment or programs with inferior algorithms.
  * Trust private consultant to make a reliable evaluation of different algorithms.
  * Trust the government, based on the belief that the government is trustworthy and the citizent is nothing wrong.
  * Trust himself/herself, write their own algorithms, based on the belief that their cryptographic ability.
  
  - It's very sensitive to use the first option to choose an algorithm. Most security product manufacturers are no better, nor trust private consultants    nor the government could offer you a good algorithm. And among public algorithms that have withstood a reasonable amount of public scrutiny and cryptanalysis.
  
  - Any algorithms for export out of the United States must be approved by the U.S. government (by the NSA). We could say like these export-approved algorithms can be broken by the NSA.
  
  
### 10.2 PUBLIC-KEY CRYPTOGRAPHY VERSUS SYMMETRIC CRYPTOGRAPHY

  - Here no sense to compare thses two ways of cryptgraphy. Needham and Schroeder pointed out the number and length of messages are far greater with public-key algorithms than with symmetric algorithms. The symmetric algorithm was more efficient than the public-key algorithm. But for the Whitfield Diffie, he pointed out the public-key cryptography and symmetric cryptography are different sorts of animals; they solve different problems. Symmetric cryptography is best for encrypting data. It is orders to be faster and is not susceptible to chosen-ciphertext attacks. Public-key cryptography can do things that symmetric cryptography can't; it is best for key management and a myriad of protocols.
  
  
### 10.3 ENCRYPTING COMMUNICATIONS CHANNELS

  - The example of Alice wants to send a secure message to Rob. 
  - If it takes place at the lowest layers, it is called link-by-link encryption; everything going through a particular data link is encrypted. If it takes     place at higher layers, it is called end-to-end encryption;
    * link-by-link encryption
      
      This type of encryption is very effective. Because everything is encrypted, a attacker can get no information about the structure of the information.
      Key management is also simple which only the two endpoints of the line need a common key, and they can change their key independently from the rest         of the network. The biggest problem with encryption at the physical layer is that each physical link in the network needs to be encrypted. Otherwise, it could be damage to the whole network.
      
      <img width="678" alt="image" src="https://user-images.githubusercontent.com/95883827/221787266-913f01ff-cde0-4ec3-ba77-89cc654f71bd.png">

    * End-to-End Encryption
      
      This is the other approach is to put encryption equipment between the network layer and the transport layer. By providing end-to-end encryption, the       data remains encrypted until it reaches its final destination. The advantage of this approach is easy to operate and ONLY one set of keys per link is       required. On the other side, this could allow the data is exposed in the intermediate nodes, it allows traffic analysis. Traffic analysis is the           analysis of encrypted messages: BUT it's DIFFICULT to build the end-to-end encryption.        

      <img width="654" alt="image" src="https://user-images.githubusercontent.com/95883827/221788424-50e6b7f6-a6ed-44c0-8880-1b564139a2a7.png">
      
    * WHAT IF COMBINING TWO OF THESE APPROACH?
      This is going to be very expensive. But you could have higher secrecy level. The disadvanta of this way is requires a more complex key-management           system. Traffic analysis is still possible, since routing information is not encrypted.


### 10.4 ENCRYPTING DATA FOR STORAGE

  - In communications channels, messages in transit have no intrinsic value. For example, IF Rob do not received the message from Alice, Alice always could resend the message to Rob.
  - The data may also exist in plaintext form, either on another disk, in another computer, or on paper. 
  - In database applications, pieces of data may be smaller than the block size of most algorithms.
  - The speed of Input/Output devices demands fast encryption and decryption, and will probably require encryption hardware. 
  - Safe, long-term storage for keys is required.
  - Key management is much more complicated, because of different people need access to different files, different portions of the same file.


## Choose a password manager. 

The password manager that I am using is KeePassXC.
<img width="237" alt="image" src="https://user-images.githubusercontent.com/95883827/221791326-ef65ec8e-bdad-4ad5-a001-593c113fbf5e.png">

- What treaths does it protect against?
  
  * Your credentials are stored locally in AES-256-encrypted database files that can only be decrypted using the correct password. Even if a hacker got a hold of your database file, it's useless to them without the ability to decrypt it.
  
- What information is encrypted, what's not?
  
  * It saves many different types of information, such as Title, Usernames, Passwords, URLs, Tags,attachments, and notes in an offline, encrypted file that can be stored in any location, including private and public cloud solutions.
  * ![image](https://user-images.githubusercontent.com/95883827/221792597-59814484-ad42-4a23-8161-b6775694da8c.png)
  *Figure 1. Main database interface
  
  * It saves many different types of information, such as Title, Usernames, Passwords, URLs, Tags,attachments, and notes in an offline, encrypted file that can be stored in any location, including private and public cloud solutions.

- What's the license? How would you describe license's effects or categorize it?

  * KeePassXC is licensed with the GNU General Public License Version 3. All copyrights and additional licenses are recorded in COPYING.

- Where is the data stored? If in "the cloud", which country / juristiction / which companies? If on local disk, where?
  
  * The database file is saved on to your computer with the default.
  * The database file that is protected with a strong and long password is secure and encrypted while stored on your computer or cloud storage service.         (e.g., OneDrive, Dropbox, Google Drive, Nextcloud, Syncthing, etc)
  
  * <img width="690" alt="image" src="https://user-images.githubusercontent.com/95883827/221792962-9579077e-73fc-4b6f-a50a-d836c9393175.png">
  
- How is the data protected?
  
  * KeePassXC is a cross-platform application written in C++ using the Qt framework. We have worked very hard to be consistent across Windows, Linux, and MacOS platforms in terms of user experience and security. It protect all data “at rest” (that is, when it is saved in the password database file *.kdbx).
