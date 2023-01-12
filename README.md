from itertools import combinations

newspapers = {'Times of India': 4.00, 'Hindu': 3.00, 'ET': 3.50, 'BM': 2.50, 'HT': 4.50}

def find_combinations(budget, newspapers):
    newspaper_combinations = [combinations(newspapers, i+1) for i in range(len(newspapers))]
    newspaper_combinations = [item for sublist in newspaper_combinations for item in sublist]
    newspaper_combinations = [comb for comb in newspaper_combinations if sum(newspapers[newspaper] for newspaper in comb) <= budget]
    return newspaper_combinations

budget = int(input("Enter your weekly budget for newspaper subscriptions: "))
print("All possible combinations of newspaper subscriptions:")
print(find_combinations(budget, newspapers))
