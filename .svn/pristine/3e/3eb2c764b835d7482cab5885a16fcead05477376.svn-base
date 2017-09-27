
public class TrailsList {
	private Trails[] data=new Trails[0];
	private int size=0;
	
	
	
	public TrailsList(){
		
	}
	
	public Trails[] getarrey(){
		return data;
	}
	
	public int getsize(){
		return size;
	}
	public void add(Trails one){

			size++;
			Trails[] old=data;
			data=new Trails[size];
			for(int i=0;i<old.length;i++){
				data[i]=old[i];
			}
			data[size-1]=one;
		
			
	}
	
	public Trails[] removeN(Trails[] data, String name){
		int size=data.length;
		for(int i=0;i<data.length;i++){
			if(data[i].getname().equals(name)){
				size--;
				Trails[] old=data;
				data=new Trails[size];
				for(int j=0;j<i;j++){
					data[j]=old[j];
				}
				for(int j=i;j<size;j++){
					data[j]=old[j+1];
				}
			}
		}
		return data;
		
	}
	
	public void remove(String name){
		for(int i=0;i<data.length;i++){
			if(data[i].getname().equals(name)){
				size--;
				Trails[] old=data;
				data=new Trails[size];
				for(int j=0;j<i;j++){
					data[j]=old[j];
				}
				for(int j=i;j<size;j++){
					data[j]=old[j+1];
				}
			}
		}
	}
	

	public static Trails[] SortT(Trails[] data){
		sortT(data);
		return data;
	}
	public static void sortT(Trails[] list){
		sort(list,0,list.length-1);
	}
	
	public static void sort(Trails[] list,int lo, int hi){
		if(hi>lo){
			swap(list,lo,findMin(list,lo,hi));
			sort(list,lo+1,hi);
		}
	}
	
	public static void swap(Trails[] list, int i, int j){
		Trails ref=list[i];
		list[i]=list[j];
		list[j]=ref;
	}
	
	public static int findMin(Trails[] list, int lo, int hi){
		if(lo==hi) return lo;
		int ref= findMin(list,lo+1,hi);
		if(list[lo].getname().compareTo(list[ref].getname())>0) return ref;
		return lo;
	}
	
	public static void print(Trails[] list){
		for(int i=0;i<list.length;i++){
			TextIO.putln(list[i].getname());
		}
	}
	
	public static void printall(Trails[] list){
		for(int i=0;i<list.length;i++){
			TextIO.put(list[i].getname()+", "+list[i].getrate()+", "+list[i].geth()+", "+list[i].getl()+", "+list[i].getstate()+", "+list[i].getland().tostring());
			if(list[i].getans()) TextIO.putln("*");
			else TextIO.putln("");
		}
	}
	
	
	
	

	public Trails[] removeR(Trails[] data, int rate){
		sortbyR(data,0,data.length-1);
		int ref=findR(data,0,data.length-1,rate);
		if(ref!=-1){
			int size=data.length;
			size-=ref;
			Trails[] old=data;
			data=new Trails[size];
			for(int i=0;i<size;i++){
				data[i]=old[i+ref];
			}
		}
		return data;
		
	}
	
	public int findR(Trails[] data, int lo, int hi, int rate){
		if(lo>hi) return -1;
		if(data[lo].getrate()>=rate) return lo;
		return findR(data,lo+1,hi,rate);
		
	}
	public void sortbyR(Trails[] data, int lo, int hi){
		if(hi>lo){
			swap(data,lo,FindMinR(data,lo,hi));
			sortbyR(data,lo+1,hi);
		}
	}
	
	public int FindMinR(Trails[] data, int lo, int hi){
		if (lo==hi) return lo;
		int result=FindMinR(data,lo+1,hi);
		if(data[result].getrate()<data[lo].getrate()) return result;
		return lo;
	}
	
	
	public TrailsList findState(String s){
		TrailsList result=new TrailsList();
		for(int i=0;i<size;i++){
			if (data[i].getstate().equals(s)){
				result.add(data[i]);
			}
		}
		sortT(result.getarrey());
		return result;
	}
	
	public TrailsList nothave(){
		TrailsList result=new TrailsList();
		for(int i=0;i<size;i++){
			if(!data[i].getans()) result.add(data[i]);
		}
		return result;
	}
	
	public int findN(String name){
		for(int i=0;i<size;i++){
			if(data[i].getname().equals(name)) return i;
		}
		return -1;
	}
	
	public static double distance(Trails a,Trails b){
		double detal=Math.abs(a.getl()-b.getl())*3.14/180;
		double h1=a.geth()*3.14/180, h2=b.geth()*3.14/180, l1=a.getl()*3.14/180, l2=b.getl()*3.14/180;
		double delta=Math.acos(Math.sin(h1)*Math.sin(h2)+Math.cos(l1)*Math.cos(l2)*Math.cos(detal));
		return 3959*delta;
	}
	
	public int findNear(Trails a, Trails[] data, int lo,int hi){
		if(lo==hi) return lo;
		int ref=findNear(a,data,lo+1,hi);
		if(distance(a,data[lo])>distance(a,data[ref])) return ref;
		return lo;
		
	}
	
	public TrailsList findland(String land){
		TrailsList result=new TrailsList();
		for(int i=0;i<size;i++){
			if(data[i].getland().tostring().indexOf(land)>=0) result.add(data[i]);
		}
		return result;
	}
	
	
	
	
	
	
	
	
	
	
	
	
}
