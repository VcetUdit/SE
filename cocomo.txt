import math

def estimate_effort(kloc, scale_factor, effort_multiplier):
    # COCOMO constants for basic model
    a = 2.5
    b = 1.2
    
    # Effort Adjustment Factor (EAF)
    eaf = scale_factor * effort_multiplier
    
    # Calculating effort in person-months
    effort = (a * math.pow(kloc, b)) * eaf
    return effort

def main():
    kloc = float(input("Enter the size of the software in KLOC: "))
    scale_factor = 1.0  # example value for scale factor
    effort_multiplier = 2.5  # example value for effort multiplier

    # Calculate and display the effort
    effort = estimate_effort(kloc, scale_factor, effort_multiplier)
    print(f"Estimated effort: {effort:.2f} person-months")

if __name__ == "__main__":
    main()