# Time-Duration-Calculation
Time Duration Calculation through agr year,month,date,hourse,minutes and second
from datetime import datetime, timedelta  
class SurvivalDurationCalculator:  
    def __init__(self, age_years: int):  
        """Initialize the calculator with the age in years."""  
        self.age_years = age_years  

    def calculate_months(self) -> int:  
        """Calculate the survival duration in months."""  
        return self.age_years * 12  

    def calculate_weeks(self) -> int:  
        """Calculate the survival duration in weeks."""  
        return self.age_years * 52  # Using 52 weeks per year for approximation  

    def calculate_days(self) -> int:  
        """Calculate the survival duration in days."""  
        return self.age_years * 365  # Using 365 days per year for approximation  

    def calculate_hours(self) -> int:  
        """Calculate the survival duration in hours."""  
        return self.calculate_days() * 24  

    def calculate_minutes(self) -> int:  
        """Calculate the survival duration in minutes."""  
        return self.calculate_hours() * 60  

    def calculate_seconds(self) -> int:  
        """Calculate the survival duration in seconds."""  
        return self.calculate_minutes() * 60  

    def summary(self) -> str:  
        """Provide a summary of the survival duration in different units."""  
        return (f"Survival Duration for {self.age_years} years:\n"  
                f"- {self.calculate_months()} months\n"  
                f"- {self.calculate_weeks()} weeks\n"  
                f"- {self.calculate_days()} days\n"  
                f"- {self.calculate_hours()} hours\n"  
                f"- {self.calculate_minutes()} minutes\n"  
                f"- {self.calculate_seconds()} seconds")  


# Main execution  
if __name__ == "__main__":  
    try:  
        age = int(input("Enter your age in years: "))  
        if age < 0:  
            print("Please enter a valid non-negative age.")  
        else:  
            calculator = SurvivalDurationCalculator(age)  
            print(calculator.summary())  
    except ValueError:  
        print("Please enter a valid number for your age.")  
