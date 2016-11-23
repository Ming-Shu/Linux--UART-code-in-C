# Linux--UART-code-in-C
 Introduces how to implement programming from serial port in C in linux.
 
 1.  Open the device file and get file descriptor.
 
     fd = open(comPort, O_RDWR | O_NOCTTY | O_NDELAY | O_NONBLOCK);
     
     char *comPort : device file path
     int fd:         create file descriptor
     
2. Settings to "termios.h"  

    tcgetattr():   setting file descriptor into a pointer that to termios structure.
    
    cfsetispeed(): set the 'inport' baud rate in the termios structure
    
    cfsetospeed(): set the 'outport'baud rate in the termios structure
    
    Set the parity enable and parity type bits
     
3. Writing Data to the Port and Reading Data from the Port (sys/types.h)
    
    write(): system call to send data.
    
    read():  system call to receive data
    
    fcntl(): performs one of the operations described below on the open file descriptor fd
    
    close(): closing a serial port
