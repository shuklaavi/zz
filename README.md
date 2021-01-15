# Get First Date and Last Date For Specific Year and Month....

 I have write a code in java Language using  YearMonth Class.
 
 YearMonth is a final class in java.time  package. which is introduce in java 8 version.
 
 public static void main(String[] args) {
	
		int year = 2021;
		int months = 6;
		YearMonth yearMonth = YearMonth.of( year, months );  
		LocalDate firstOfMonth = yearMonth.atDay( 1 );
		String startdate = firstOfMonth.toString();
		LocalDate lastOfMonth = yearMonth.atEndOfMonth();
		String enddate = lastOfMonth.toString();
	    System.out.println(startdate);
	    System.out.println(enddate);
	}
