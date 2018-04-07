package sda.java9.wpj.basics;

class SeasonOfTheYear
{
	public static void main (String [] args) 
	{
		String season = season (12,28);
		System.out.println(season);
		
	}
	
	public static boolean isValidDayOfMonth(int month, int dayOfMonth)
	{
		if (dayOfMonth <= 0 || dayOfMonth > 31) //to od razu załatwia sprawę miesięcy 31 dniowych
		{
			return false; 
		}
		switch (month) 
		{
			case 2:
				return dayOfMonth <= 29;
			case 4:
			case 6:
			case 9:
			case 11:
				return dayOfMonth <=30;
			
		}
		return true;
	}
	
	public static String season(int month, int dayOfMonth) 
	{
		if (!isValidDayOfMonth(month, dayOfMonth))
		{
			throw new IllegalArgumentException("Dla miesiąca " + month + " podany dzien nie itnieje, podano dzień: " + dayOfMonth);
		}
			
		switch (month)
		{	case 1:
			case 2:
					return "Zima";
			case 3:
				if (dayOfMonth < 21) 
				{
					return "Zima";
				}
				else 
				{
					return "Wiosna";
				}
			case 4:
			case 5:
					return "Wiosna";
			case 6:
				if (dayOfMonth < 22)
				{
					return "Wiosna";
				}
				else
				{
					return "Lato";
				}
			case 7:
			case 8:
					return "Lato";
			case 9:
				if (dayOfMonth < 23)
				{
					return "Lato";
				}
				else
				{
					return "Jesien";
				}
			case 10:
			case 11:
					return "Jesien";
			case 12:
				if (dayOfMonth < 22)
				{
					return "Jesien";
				}
				else
				{
					return "Zima";
				}
			default :
				throw new IllegalArgumentException("Dla miesiąca " + month + " podany dzien nie itnieje, podano dzień: " + dayOfMonth);
		}
	
	}
	
}
