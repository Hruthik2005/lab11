package mama.mama;

import java.io.*;
import org.json.simple.*;
import org.json.simple.parser.*;

public class Readjson {

    public static void main(String[] args)
            throws IOException, ParseException {

        JSONParser parser = new JSONParser();  // changed name

        FileReader reader = new FileReader("./JSON/student.json");

        Object obj = parser.parse(reader);      // using parser
        JSONObject studentobj = (JSONObject) obj;

        String fname = (String) studentobj.get("firstname");
        String lname = (String) studentobj.get("lastname");

        System.out.println("Firstname: " + fname);
        System.out.println("Lastname: " + lname);

        reader.close();
    }
}
