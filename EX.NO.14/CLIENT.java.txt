package client;
import java.util.*;
public class Client {

    public static void main(String[] args) {
               Scanner scanner = new Scanner(System.in);
           for(int i=0;i<3;i++)
           {
            System.out.print("Product name: ");
            String productname = scanner.nextLine();
            System.out.print("Price: ");
            double price = Double.parseDouble(scanner.nextLine());
    productorder(productname,price);
    String result=productorder(productname,price);
     System.out.print(result);
    
           }   
    }

    private static String productorder(java.lang.String productname, double price) {
        service.NewWebService_Service service = new service.NewWebService_Service();
        service.NewWebService port = service.getNewWebServicePort();
        return port.productorder(productname, price);
    }
    
}
