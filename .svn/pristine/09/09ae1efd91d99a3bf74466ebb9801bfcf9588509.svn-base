
public class HappyTrails {
	public static void main(String[] args) {
		TrailsList list=new TrailsList();
		boolean running=true;
		int state=0;
		while(running){
			
			 //main menu
			if(state==0){                                            
			TextIO.putln("Welcome to Happy Trails! Select an option below:\n"+"\n"+"1) add a hiking trail\n"+"2) remove a hiking trail\n"+"3) display hiking trails alphabetically\n"
		+"4) display hiking trails >= a certain rating\n"+"5) display hiking trails in a specified state\n"+"6) display the nearest hiking trail to specified hiking trail\n"
					+"7) list all trails with a specified landmark\n"+"8) list all hiking trails the user has yet to hike\n"+"9) quit\n\n"+"Select an option above:");
			state=TextIO.getlnInt();
			}
			
			if(state==9){
				TextIO.putln("Are you sure you want to quit? (yes/no)- all your data will be lost.");
				String ans=TextIO.getln();
				if (ans.equals("yes")){
					TextIO.putln("Bye~");
					running=false;
				}
				else state=0;	
			}
			
			//add function.
			while(state==1){                                                 
				TextIO.putln("please enter the name:");
				String name=TextIO.getln();
				TextIO.putln("please enter the rate (1-5):");
				int rate=TextIO.getlnInt();
				while(rate<1||rate>5){
					TextIO.putln("please enter the rate (1-5):");
					rate=TextIO.getlnInt();
				}
				TextIO.putln("please enter the latitude(-90--90, positive means north, negative means south):");
				double h=TextIO.getlnInt();
				TextIO.putln("please enter the longitude(-180--180, positive means east, negative means west):");
				double l=TextIO.getlnInt();
				TextIO.putln("please enter the state abbreviation:");
				String s=TextIO.getln();
				TextIO.putln("have you hiked it?(yes/no)");
				String ans=TextIO.getln();
				boolean a;
				if(ans.equals("yes")) a=true;
				else a=false;
				TextIO.putln("Do you wanna add a landmark? If so, enter the landmarks. Otherwise enter no.");
				String landmark=TextIO.getln();
				LandmarkList landlist= new LandmarkList();
				while(!landmark.equals("no")){
					landlist.add(landmark);
					TextIO.putln("Add one more?(if so enter the landmark, otherwise enter no)");
					landmark=TextIO.getln();
				}
				Trails one=new Trails(name,rate,h,l,s,a,landlist);
				list.add(one);
				TextIO.putln("Do you wanna add one more trail?(yes/no)");
				String a2=TextIO.getln();
				if(a2.equals("yes")) state=1;
				else state=0;
			}
			
			
			//remove function
			while(state==2){                 
				TrailsList.sortT(list.getarrey());
				TrailsList.print(list.getarrey());
				TextIO.putln("please enter the name of the trial you wanna remove:");
				String name=TextIO.getln();
				int ref=list.getsize();
				list.remove(name);
				if(ref==list.getsize()){
					TextIO.putln("the name you entered is not existed.");
					state=2;
				}
				else {
					TextIO.putln("Do you wanna remove one more?(yes/no)");
					String ans=TextIO.getln();
					if(ans.equals("yes")) state=2;
					else state=0;
				}
				if(list.getsize()==0){
					TextIO.putln("There is no more trail in the database. Enter anything to return the main menu.");
					String any=TextIO.getln();
					state=0;
				}
			}
			
			//display trails alphabetically.
			if(state==3){
				TrailsList.sortT(list.getarrey());
				TrailsList.printall(list.getarrey());
				TextIO.putln("Enter anything to return the main menu.");
				String any=TextIO.getln();
				state=0;
			}
			
			//display trails at a certain rating
			if(state==4){
				TextIO.putln("Please enter a integer rating(1-5):");
				int r=TextIO.getlnInt();
				Trails[] result=list.removeR(list.getarrey(), r);
				result=TrailsList.SortT(result);
				TrailsList.printall(result);
				TextIO.putln("Enter anything to return the main menu.");
				String any=TextIO.getln();
				state=0;
			}
			
			
			//display trails in a specific state
			if(state==5){
				TextIO.putln("Please enter a state abbreviation");
				String sname=TextIO.getln();
				TrailsList result=list.findState(sname);
				result=result.nothave();
				TrailsList.printall(result.getarrey());
				TextIO.putln("Enter anything to return the main menu.");
				String any=TextIO.getln();
				state=0;
			}
			
			if(state==6){
				TextIO.putln("Please enter a name of the trail:");
				String name=TextIO.getln();
				Trails one=list.getarrey()[list.findN(name)];
				Trails[] result=list.removeN(list.getarrey(), name);
				int i=list.findNear(one,result,0,result.length-1);
				Trails.printTrails(result[i]);
				TextIO.putln("Distance: "+TrailsList.distance(one, list.getarrey()[i])+" miles");
				TextIO.putln("Enter anything to return the main menu.");
				String any=TextIO.getln();
				state=0;
				
				
			}
			
			if(state==8){
				TrailsList not=list.nothave();
				Trails[] ref=TrailsList.SortT(not.getarrey());
				TrailsList.print(ref);
				not.sortbyR(not.getarrey(),0,not.getarrey().length-1);
				String result=not.getarrey()[not.getarrey().length-1].getname();
				TextIO.putln("We recommend hiking: "+result);
				TextIO.putln("Enter anything to return the main menu.");
				String any=TextIO.getln();
				state=0;
				
			}
			
			if(state==7){
				TextIO.putln("Please enter a landmark:");
				String land=TextIO.getln();
				TrailsList haveland=list.findland(land);
				Trails[] ref=TrailsList.SortT(haveland.getarrey());
				TrailsList.printall(ref);
				TextIO.putln("Enter anything to return the main menu.");
				String any=TextIO.getln();
				state=0;
			}
			
			
		}
		
		// TODO Auto-generated method stub

	}
	
	


}
