# cn-

# simple chat 

```java
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

# arp 
```java 
import java.io.BufferedReader;
import java.io.DataOutputStream;
import java.io.InputStreamReader;
import java.net.*;
public class ClientARP {
    public static void main(String[] args) {
        try {
            BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
            Socket s =  new Socket("localhost", 7594);
            //DataInputStream dis = new DataInputStream(s.getInputStream());
            DataOutputStream dos = new DataOutputStream(s.getOutputStream());
            System.out.println("ENTER LODICAL ADDRESS : ");
            String str1 = bf.readLine();
            dos.writeBytes(str1);
            String str = bf.readLine();
            System.out.println("THE PHYSICAL ADDRESS IS "+ str);
            dos.close();
            s.close();

        } catch (Exception e) {
            
        }
    }
}

import java.io.DataInputStream;
import java.io.DataOutputStream;
import java.net.ServerSocket;
import java.net.Socket;

public class ServerARP {
    public static void main(String[] args) {
        try {
            ServerSocket ss = new ServerSocket(7594);
            Socket s = ss.accept();
            while(true){
                DataInputStream dis = new DataInputStream(s.getInputStream());
                DataOutputStream dos = new DataOutputStream(s.getOutputStream());
                System.out.println("ENTER LOGICAL ADDRESS IS ");
                String str= dis.readLine();
                String ip[] ={"111.55.90.80", "170.165.79.1"};
                String mac[] ={"6A:08:AB:C2", "8A:AC:E3:FA"};
                for(int i=0;i<ip.length;i++){
                    if(str.equals(ip[i])){
                        dos.writeBytes(mac[i]);
                        break;
                    }
                }
                ss.close();
            }

        } catch (Exception e) {
        }

    }
}


```
# tracert

```java 
import java.io.BufferedReader;
import java.io.InputStreamReader;

public class tracent {
    public static void Runcommand(String Command){
        try {
            Process p = Runtime.getRuntime().exec(Command);
            BufferedReader bf = new BufferedReader(new InputStreamReader(p.getInputStream()));
            String s ="";
            while((s=bf.readLine())!=null){
                System.out.println(s);
            }

        } catch (Exception e) {
            //TODO: handle exception
            e.printStackTrace();
        }
    }
    public static void main(String[] args) {
        String ip="67.195.160.76";
        Runcommand("TRACEROUTE "+ip);
        java.util.Date d = new java.util.Date();
        System.out.println(d);
    }
}

```

# ping 

```java 
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.lang.Process;

public class ping {
    public static void Runcommand(String Command){
        try {
            Process p = Runtime.getRuntime().exec(Command);
            BufferedReader bf = new BufferedReader(new InputStreamReader(p.getInputStream()));
            String s ="";
            while((s=bf.readLine())!=null){
                System.out.println(s);
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
        
    }
    public static void main(String[] args) {
        String ip="localhost";
        Runcommand(ip);
        java.util.Date date = new java.util.Date();
        System.out.println(date);
    }
}

```
# rarp 
```java 
import java.io.BufferedReader;
import java.io.DataOutputStream;
import java.io.InputStreamReader;
import java.net.*;
public class ClientARP {
    public static void main(String[] args) {
        try {
            BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
            Socket s =  new Socket("localhost", 7594);
            //DataInputStream dis = new DataInputStream(s.getInputStream());
            DataOutputStream dos = new DataOutputStream(s.getOutputStream());
            System.out.println("ENTER LODICAL ADDRESS : ");
            String str1 = bf.readLine();
            dos.writeBytes(str1);
            String str = bf.readLine();
            System.out.println("THE PHYSICAL ADDRESS IS "+ str);
            dos.close();
            s.close();

        } catch (Exception e) {
            
        }
    }
}

import java.io.DataInputStream;
import java.io.DataOutputStream;
import java.net.ServerSocket;
import java.net.Socket;

public class ServerARP {
    public static void main(String[] args) {
        try {
            ServerSocket ss = new ServerSocket(7594);
            Socket s = ss.accept();
            while(true){
                DataInputStream dis = new DataInputStream(s.getInputStream());
                DataOutputStream dos = new DataOutputStream(s.getOutputStream());
                System.out.println("ENTER LOGICAL ADDRESS IS ");
                String str= dis.readLine();
                String ip[] ={"111.55.90.80", "170.165.79.1"};
                String mac[] ={"6A:08:AB:C2", "8A:AC:E3:FA"};
                for(int i=0;i<mac.length;i++){
                    if(str.equals(mac[i])){
                        dos.writeBytes(ip[i]);
                        break;
                    }
                }
                ss.close();
            }

        } catch (Exception e) {
        }

    }
}

```


# echo server

```java 
package networks;
import java.net.InetAddress;
import java.net.Socket;
import java.io.DataInputStream;
import java.io.PrintStream;

public class eclient {
    public static void main(String[] args) {
        try {
            InetAddress id = InetAddress.getLocalHost();
            Socket s = new Socket(id, 7594);
            String line ="";
            PrintStream ps = new PrintStream(s.getOutputStream());
            DataInputStream dis = new DataInputStream(System.in);
            DataInputStream dis1 = new DataInputStream(s.getInputStream());
            while(true){
                System.out.println("CLIENT : ");
               // line=dis.readInt();
                ps.println(line);
                
            }

        } catch (Exception e) {
            System.out.println(e);
        }
    }
}


```
