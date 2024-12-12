# PPL-project
# voting System
class VotingSystem:
    def __init__(self):
        # Initialize the candidates and their votes
        self.candidates = {}
        
    def add_candidate(self, candidate_name):
        # Add a candidate with initial vote count as 0
        if candidate_name not in self.candidates:
            self.candidates[candidate_name] = 0
            print(f"Candidate {candidate_name} added successfully!")
        else:
            print(f"Candidate {candidate_name} already exists.")

    def vote(self, candidate_name):
        # Register a vote for a candidate
        if candidate_name in self.candidates:
            self.candidates[candidate_name] += 1
            print(f"Vote registered for {candidate_name}!")
        else:
            print(f"Candidate {candidate_name} does not exist.")
    
    def show_results(self):
        # Display the voting results
        print("\nVoting Results:")
        for candidate, votes in self.candidates.items():
            print(f"{candidate}: {votes} votes")
            
# Driver code
if __name__ == "__main__":
    voting_system = VotingSystem()
    
    while True:
        print("\n--- Voting System ---")
        print("1. Add Candidate")
        print("2. Vote")
        print("3. Show Results")
        print("4. Exit")
        
        choice = input("Enter your choice (1/2/3/4): ")
        
        if choice == "1":
            candidate_name = input("Enter the name of the candidate to add: ")
            voting_system.add_candidate(candidate_name)
        elif choice == "2":
            candidate_name = input("Enter the name of the candidate to vote for: ")
            voting_system.vote(candidate_name)
        elif choice == "3":
            voting_system.show_results()
        elif choice == "4":
            print("Exiting the voting system...")
            break
        else:
            print("Invalid choice. Please try again.")
