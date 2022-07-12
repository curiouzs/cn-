# cn-

# exp 1
```java
package networks;

import java.io.*;
import java.net.*;

class ClientExp1{
    public static void main(String[] args) {
        try {
            Socket s  = new Socket("localhost" , 7594);
            DataOutputStream dos = new DataOutputStream(s.getOutputStream());
            dos.writeUTF("HELLO LOKESH");
            dos.close();
            s.close();

        } catch (Exception e) {
            System.out.println("ERROR");
        }
    }
}

package networks;

import java.io.DataInputStream;
import java.net.ServerSocket;
import java.net.Socket;

public class ServerExp1 {
    public static void main(String[] args) {
        try {
            ServerSocket ss = new ServerSocket(7594);
            Socket s = ss.accept();
            DataInputStream dis = new DataInputStream(s.getInputStream());
            String str = dis.readUTF();
            System.out.println("String  is : "+ str);
            ss.close();

        } catch (Exception e) {
            //TODO: handle exception
            System.out.println(e);
        }
    }
}

```
