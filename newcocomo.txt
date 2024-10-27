import math    #library to use math.pow function

def estimate_effort(kloc,scale_factor,effort_multiplier):
    a = 2.5  #a and b are constant values used in cocomo, its values are according to 3 types embedded,organic or semi detached
    b = 1.2  #these are values for organic since the sum is of intermediate cocomo

    eaf = scale_factor * effort_multiplier  #formula for eaf

    effort = (a * math.pow(kloc,b)) * eaf  #formula for effort. Meaning effort = (a x (kloc)^b) x eaf
    return effort

def main():
    kloc_UserModule = float(input("Enter the size of KLOC for UserModule:")) #input
    kloc_CameraDetectionModule = float(input("Enter the size of KLOC for CameraDetectionModule")) #input
    kloc_ImageProcessingModule = float(input("Enter the size of KLOC for ImageProcessingModule:")) #input
    kloc_VoiceModulationModule = float(input("Enter the size of KLOC for VoiceModulationModule:")) #input

    scale_factor = 1.0 #assumed values
    effort_multiplier = 2.5 #assumed values

    effort1= estimate_effort(kloc_UserModule,scale_factor,effort_multiplier) #the function returns effort value which we put into effort of each module
    effort2= estimate_effort(kloc_CameraDetectionModule,scale_factor,effort_multiplier) #the function returns effort value which we put into effort of each module
    effort3= estimate_effort(kloc_ImageProcessingModule,scale_factor,effort_multiplier) #the function returns effort value which we put into effort of each module
    effort4= estimate_effort(kloc_VoiceModulationModule,scale_factor,effort_multiplier) #the function returns effort value which we put into effort of each module

    print(f"The total calculated effort is: {effort1+effort2+effort3+effort4:.2f} person-months") #addition of all efforts. Note {} brackets. .2f indicates that answer should contain only 2 numbers after decimal point

if __name__ == "__main__": #formality
    main()



