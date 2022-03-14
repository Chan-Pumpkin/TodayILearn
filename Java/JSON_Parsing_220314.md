```java
import java.io.FileReader;
import java.io.IOException;
import java.io.Reader;

import org.json.simple.JSONArray;
import org.json.simple.JSONObject;
import org.json.simple.parser.JSONParser;
import org.json.simple.parser.ParseException;

public class JsonCrawling {

	public static void main(String[] args) throws IOException {
		// TODO Auto-generated method stub
		
		try { 
			
			Reader reader = new FileReader("D:\\crawlingTest\\part0.json");
			
			JSONParser jsonParse = new JSONParser(); //JSONParse에 json데이터를 넣어 파싱한 다음 JSONObject로 변환한다. 
			JSONObject jsonReader = (JSONObject) jsonParse.parse(reader); //JSONObject에서 PersonsArray를 get하여 JSONArray에 저장한다. 
			
			String a = (String) jsonReader.get("callidentifier");// 1층
			System.out.println(a);
			
			JSONObject aa = (JSONObject) jsonReader.get("granted");// 1층(상위)
			String aabb = (String) aa.get("currency"); //2층(하위)
			Double aabb1 = (Double) aa.get("fundedamount"); //2층(하위)
			Double aabb2 = (Double) aa.get("totalcost"); //2층(하위)
			System.out.println(aabb);
			System.out.println(aabb1);
			System.out.println(aabb2);
			
			
			JSONArray aaArray = (JSONArray) jsonReader.get("funding"); // 1층 배열(상위)
			
			for(int i=0; i<aaArray.size(); i++){
				JSONObject result = (JSONObject) aaArray.get(i); // 2층 배열(하위) 
				JSONObject result2 = (JSONObject) result.get("funding_stream"); // 3층(2층 배열((하위)의 하위))
				System.out.println(result2.get("description"));
				System.out.println(result2.get("id"));
				
				System.out.println(result.get("jurisdiction"));
				System.out.println(result.get("name")); 
				System.out.println(result.get("shortName")); 
				}
			} 
		catch (ParseException e) { 
			e.printStackTrace(); 
			}

	}

}
```
