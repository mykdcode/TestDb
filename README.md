# TestDb
test databases
package testDb;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

public class TestDb {
	
	  public static void main(String[] args)
	    {
	    	getOracleConnection();
	    }
    private static Connection getOracleConnection(){
       // initParams();
        Connection conn = null;
        try {
            Class.forName("oracle.jdbc.driver.OracleDriver").newInstance();   
            System.out.println("start test");
        conn= DriverManager.getConnection("jdbc:oracle:thin:@10.157.171.91:11521/eicdb","PLATFORM","CJcx171pla");
         //   conn= DriverManager.getConnection("jdbc:oracle:thin:@127.0.0.1:1521:orcl","PLATFORM","PLATFORM");
            System.out.println("succeed");
        } catch (ClassNotFoundException e) {
            e.printStackTrace();
            System.out.println("Oracle notfound");
          
        } catch (InstantiationException e) {
            e.printStackTrace();
            System.out.println("fail init");
        } catch (IllegalAccessException e) {
            e.printStackTrace();
            System.out.println("IllegalAccessException");
        } catch (SQLException e) {
            e.printStackTrace();
            System.out.println("SQLException");
        }
        return conn;
    }

  
}
