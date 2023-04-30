package service;
import java.sql.*;
import javax.jws.WebService;
import javax.jws.WebMethod;
import javax.jws.WebParam;
import javax.ejb.Stateless;

@WebService(serviceName = "NewWebService")
@Stateless()
public class NewWebService {

    @WebMethod(operationName = "productorder")
    public String productorder(@WebParam(name = "productname") String productname, @WebParam(name = "price") double price) 
    {
        try{
           
            Connection con = DriverManager.getConnection ("jdbc:derby://localhost:1527/Productsdb ");
            Statement stmt = con.createStatement();
   String sql=" INSERT INTO PRODUCTSORDER values('"+productname+"',"+price+")";
            int a = stmt.executeUpdate(sql);
            if (a==1){
                System.out.println("Successfully Inserted");
            }
            else{
                System.out.println("Error in insertion!");  
        }
        }
        catch (Exception ex) {
           
            System.err.println(ex);
        }
           
        return "Successfully Inserted!";
}
}