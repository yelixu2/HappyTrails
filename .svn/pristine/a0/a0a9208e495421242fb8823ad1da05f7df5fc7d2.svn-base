
public class LandmarkList {
	private String[] data=new String[0];
	private int size=0;
	
	public LandmarkList(){
		
	}
	
	public void add(String one){
		size++;
		String[] old=data;
		data=new String[size];
		for(int i=0; i<old.length;i++){
			data[i]=old[i];
		}
		data[size-1]=one;
	}
	
	public int getsize(){
		return size;
	}
	
	public String tostring(){
		String result="";
		for(int i=0;i<size-1;i++){
			result+=data[i]+"; ";
		}
		result+=data[size-1]+".";
		return result;
	}

}
