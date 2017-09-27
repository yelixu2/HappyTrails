
public class Trails {
	private String name, state;
	private int rate;
	private double latitude, longitude;
	private boolean haveHiked;
	private LandmarkList landlist;
	
	public Trails(String name, int rate, double h, double l, String state, boolean have, LandmarkList landlist){
		this.name=name;
		this.rate=rate;
		latitude=h;
		longitude=l;
		this.state=state;
		haveHiked=have;
		this.landlist=landlist;
	}
	
	public String getname(){
		return name;
	}
	
	public int getrate(){
		return rate;
	}
	
	public double geth(){
		return latitude;
	}
	
	public double getl(){
		return longitude;
	}
	
	public boolean getans(){
		return haveHiked;
	}
	
	public String getstate(){
		return state;
	}
	
	public LandmarkList getland(){
		return landlist;
	}
	
	public static void printTrails(Trails one){
		TextIO.put(one.name+", "+one.rate+", "+one.latitude+", "+one.longitude+", "+one.state+", "+one.landlist.tostring());
		if(one.haveHiked) TextIO.putln("*");
		else TextIO.putln("");
		
	}
}
