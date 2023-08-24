# Lab4_DeekshaAilawadi
This is my first comment_DeekshaAilawadi Value 1

class FlightTable:
    def __init__(self):
        self.matches = []

    def add_match(self, location, teams, timing):
        self.matches.append({
            "Location": location,
            "Teams": teams,
            "Timing": timing
        })

    def get_matches_by_team(self, team_name):
        return [match for match in self.matches if team_name in match["Teams"]]

    def get_matches_by_location(self, location):
        return [match for match in self.matches if match["Location"] == location]

    def get_matches_by_timing(self, timing):
        return [match for match in self.matches if match["Timing"] == timing]


def main():
    flight_table = FlightTable()

    flight_table.add_match("Mumbai", ["India", "England"], "DAY")
    flight_table.add_match("Delhi", ["India", "England"], "DAY-NIGHT")
    flight_table.add_match("Chennai", ["Australia", "India"], "DAY")
    flight_table.add_match("Indore", ["India", "Australia"], "DAY-NIGHT")
    flight_table.add_match("Mohali", ["Australia", "India"], "DAY")
    flight_table.add_match("Delhi", ["South Africa", "Australia"], "DAY-NIGHT")

    while True:
        print("\nSearch Options:")
        print("1. List of all the matches of a Team")
        print("2. List of Matches on a Location")
        print("3. List of Matches based on timing")
        print("4. Exit")

        choice = int(input("Enter your choice: "))

        if choice == 1:
            team_name = input("Enter team name: ")
            matches = flight_table.get_matches_by_team(team_name)
            if matches:
                print("Matches:")
                for match in matches:
                    print(match)
            else:
                print("No matches found for the given team.")

        elif choice == 2:
            location = input("Enter location: ")
            matches = flight_table.get_matches_by_location(location)
            if matches:
                print("Matches:")
                for match in matches:
                    print(match)
            else:
                print("No matches found for the given location.")

        elif choice == 3:
            timing = input("Enter timing: ")
            matches = flight_table.get_matches_by_timing(timing)
            if matches:
                print("Matches:")
                for match in matches:
                    print(match)
            else:
                print("No matches found for the given timing.")

        elif choice == 4:
            print("Exiting...")
            break

        else:
            print("Invalid choice. Please choose a valid option.")


if __name__ == "__main__":
    main()
