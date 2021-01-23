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









#Get Data with Column Name and It's Values  (In Key-Value Pair) using JDBC


/*Template class with a basic set of JDBC operations, allowing the use
  of named parameters rather than traditional '?' placeholders.
 
  <p>This class delegates to a wrapped {@link #getJdbcOperations() JdbcTemplate}
  once the substitution from named parameters to JDBC style '?' placeholders is
  done at execution time. It also allows for expanding a {@link java.util.List}
  of values to the appropriate number of placeholders.
 
  <p>The underlying {@link org.springframework.jdbc.core.JdbcTemplate} is
  exposed to allow for convenient access to the traditional
  {@link org.springframework.jdbc.core.JdbcTemplate} methods.*/


@Autowired
protected  NamedParameterJdbcTemplate jdbc;


@GetMapping("/showDataUsingQuery/{Query}")
	public List<Map<String,Object>> ShowColumNameAndValue(@PathVariable("Query")String Query) throws SQLException {

      /* MapSqlParameterSource class is intended for passing in a simple Map of parameter values
        to the methods of the {@link NamedParameterJdbcTemplate} class*/

       MapSqlParameterSource msp = new MapSqlParameterSource();

       // this querry used for show column name and columnvalues....
		List<Map<String,Object>> css = jdbc.queryForList(Query,msp);

		return css;
	}
