def calculate_CAF(scale):
    F = 14 * scale
    CAF = 0.65 + (0.01 * F)
    return CAF

def calculate_UFP(user_input, user_output, user_inquiries, user_files, external_interface):
    UFP = (user_input * 4) + (user_output * 5) + (user_inquiries * 4) + (user_files * 10) + (external_interface * 7)
    return UFP

def calculate_FP(UFP, CAF):
    return UFP * CAF

def main():
    # Collecting input from the user
    user_input = int(input("Enter the number of User Inputs: "))
    user_output = int(input("Enter the number of User Outputs: "))
    user_inquiries = int(input("Enter the number of User Inquiries: "))
    user_files = int(input("Enter the number of User Files: "))
    external_interface = int(input("Enter the number of External Interfaces: "))
    scale = int(input("Enter the Complexity Adjustment Scale (0 to 5): "))

    # Calculating CAF, UFP, and FP
    CAF = calculate_CAF(scale)
    UFP = calculate_UFP(user_input, user_output, user_inquiries, user_files, external_interface)
    FP = calculate_FP(UFP, CAF)

    # Displaying the results
    print(f"Unadjusted Function Points (UFP): {UFP}")
    print(f"Complexity Adjustment Factor (CAF): {CAF:.2f}")
    print(f"Final Function Points (FP): {FP:.2f}")

if __name__ == "__main__":
    main()