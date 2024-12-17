# Minimum-Bags-for-Fruits

Alex has harvested N kilograms of fruits and needs to pack them for transport. He has M types of polybags available, each with a specific capacity, p[i], indicating how many kilograms it can hold. Can you help Alex figure out the minimum number of polybags he’ll need to carry all N kilograms of fruits?

def minimum_bags_for_fruits(N, M, capacities):
    capacities.sort(reverse=True)
    total_weight = 0
    bag_count = 0
    
    for capacity in capacities:
        total_weight += capacity
        bag_count += 1
        
        if total_weight >= N:
            break
    
    print(bag_count)

if __name__ == "__main__":
    N, M = map(int, input().split())  # Total weight and number of polybag types
    capacities = list(map(int, input().split()))  # List of polybag capacities
    
    minimum_bags_for_fruits(N, M, capacities)
