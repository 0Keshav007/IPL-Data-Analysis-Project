# IPL-Data-Analysis-Project
import pandas as pd
impor
t matplotlib.pyplot as plt
import seaborn as sns

# Sample IPL Data (Replace this with a comprehensive dataset for real analysis)
data = {
    'season': [2023, 2023, 2023, 2022, 2022, 2022, 2021, 2021, 2021],
    'team1': ['MI', 'CSK', 'RCB', 'MI', 'KKR', 'CSK', 'DC', 'RCB', 'MI'],
    'team2': ['CSK', 'RCB', 'MI', 'KKR', 'CSK', 'MI', 'RR', 'CSK', 'KKR'],
    'winner': ['MI', 'CSK', 'MI', 'MI', 'KKR', 'CSK', 'DC', 'RCB', 'MI'],
    'city': ['Mumbai', 'Chennai', 'Bangalore', 'Kolkata', 'Chennai', 'Mumbai', 'Delhi', 'Bangalore', 'Kolkata'],
    'player_of_match': ['Rohit Sharma', 'MS Dhoni', 'Virat Kohli', 'Jasprit Bumrah', 'Andre Russell', 'Ravindra Jadeja', 'Rishabh Pant', 'AB de Villiers', 'Kieron Pollard'],
    'runs_scored': [168, 188, 175, 150, 200, 190, 179, 185, 165]
}

ipl_df = pd.DataFrame(data)

# 1. Basic Data Exploration
print("\n--- Basic Data Exploration ---")
print(ipl_df.head())
print(ipl_df.info())

# 2. Team Performance Analysis
team_wins = ipl_df['winner'].value_counts()
print("\n--- Team Wins ---")
print(team_wins)

# Bar chart of team wins
plt.figure(figsize=(8, 6))
sns.countplot(x='winner', data=ipl_df, palette='Set2')
plt.title('Number of Wins by Team')
plt.xlabel('Team')
plt.ylabel('Number of Wins')
plt.show()

# 3. Player of the Match Analysis
player_of_match_counts = ipl_df['player_of_match'].value_counts()
print("\n--- Player of the Match Counts ---")
print(player_of_match_counts)

# Bar chart of player of the match counts
plt.figure(figsize=(10, 6))
player_of_match_counts.plot(kind='bar', color='skyblue')
plt.title('Player of the Match Awards')
plt.xlabel('Player')
plt.ylabel('Counts')
plt.show()

# 4. Runs Scored Analysis
average_runs_per_match = ipl_df['runs_scored'].mean()
print("\n--- Average Runs Scored per Match ---")
print(f"Average Runs Scored: {average_runs_per_match}")

# Histogram of runs scored
plt.figure(figsize=(8, 5))
plt.hist(ipl_df['runs_scored'], bins=8, color='purple', edgecolor='black')
plt.title('Distribution of Runs Scored per Match')
plt.xlabel('Runs Scored')
plt.ylabel('Frequency')
plt.show()

# 5. Additional Analysis: Correlation (if applicable)
# Example of finding correlation between numerical variables
correlation_matrix = ipl_df[['runs_scored']].corr()
print("\n--- Correlation Matrix ---")
print(correlation_matrix)

# Concluding Statement
print("\nData analysis and visualization completed for the IPL dataset.")
