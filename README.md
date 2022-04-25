# SIMPLE-PROJECT-OF-DISPLAYING-WELCOME-TO-EEE-DPRT-USING-ARDUINO-AND-LCD
# Abstract 
A liquid crystal display, or LCD, is a video display that utilizes the light modulating properties of liquid crystals to display pictures or text on a screen, to replace traditional cathode ray tubes 
(CRT) as a more effective option. Since their invention in 1964, LCD screens have grown to be used in a very wide variety of applications, including computer monitors, televisions, and instrument panels as the management of Waste Electrical and Electronic Equipment recycling (WEEE). One way to utilize an LCD is with an Arduino microcontroller. By wiring an Arduino microcontroller to the pins of an LCD display it is possible to program the microcontroller to display a desired text string or image on the screen. In this project, we are interfacing Liquid crystal display with Arduino to display “WELCOME TO EEE DPRT”. 
Our project will be Used as the direction to the people to direct them to EEE DPRT.

# STATEMENT OF THE PROBLEM 
The display of some electronic devices of today, Liquid crystal displays (LCD) serve as user interfaces in a wide range of applications including notebooks, desktop monitors, cell phones and other consumer and business electronics. LCD technology is rapidly replacing traditional cathode ray tubes (CRT), Seven segment displays and labels attached to the doors to provide information to the entry of rooms, as a more effective option. 
The display of text using Seven segment display require a variety number a Seven segment display devises and if one LED of a Seven segment display is damaged some texts will not be displayed. The information provided on labels attached to the doors of the entrance of rooms are not visible when there is no source of light because some of those labels are papers, woods, plastics or metals. The Display using CRTs provides Waste Electrical and Electronic Equipment recycling (WEEE). The more Seven segment used, the more they are costly. Even those labels need to be replaced many times and it requires a big amount of money.

LCDs contain substantially less materials per unit than CRTs, and the lower weight of LCDs 
enables a wide range of new applications. LCDs also consume less energy during use and are not vulnerable to overheating. The lower energy consumption also gives an advantage with regard to 
a lower potential of electromagnetic radiation causing adverse effects on biological matter. In our projects, the content(text) to be displayed on LCD can be changed any time without ant extra cost by changing the Arduino codes.
 Due to the steady increase in LCDs since the mid 1990s, a significant and 
ever rising number of disposed LCDs is to be expected in the following years. Presently, end-of-
life LCDs are stored, or crushed to be used in steel and zinc smelters and in the manufacture of 
concrete or asphalt. However, a considerable amount ends up in landfills and, therefore, there is 
a worldwide demand for an environmentally sound and ecologically sustainable method for LCD 
recovery. 

# BLOCK DIAGRAM
![image](https://user-images.githubusercontent.com/104151424/165169454-9448350f-f5de-429f-9838-cc21a2d9dfec.png)


  # DESCRIPTION

The Arduino board will be supplied by a 7 to 12 V power supply in order to perform the desired function. Then after Arduino is supplied by a 7 to 12V power supply, the board will need to be programed by Arduino source code written and compiled then uploaded from Arduino IDE software. After uploading the codes in Arduino board, the code will let the 16*2 Liquid crystal display to be able to display the text written in LCD. Print line of the Arduino IDE software and will be displayed depending on the executions of void loop of the program.

# SOURCE CODE
#include <LiquidCrystal.h> // include the library

LiquidCrystal lcd(12, 11, 7, 6, 5, 4); // define the arduino pins
              //rs, en, d4, d5, d6, d7 lcd pins
char * LargeText = " WELCOME TO EEE DPRT           ";
int iLineNumber = 1;
int iCursor = 0;
void setup()
 {
  lcd.begin(16,2);
  lcd.setCursor(1,0);
  lcd.print("RP/IPRC MUSANZE");
}
void loop()
{
  UpdateLCDDisplay();
delay(500);
  }
  void UpdateLCDDisplay()
  {
    int iLenofLargeText = strlen(LargeText);
    if (iCursor==(iLenofLargeText - 1))
    {
      iCursor = 0;
      }
      lcd.setCursor(0,iLineNumber);
      if(iCursor<iLenofLargeText -29)
      {
        for(int iChar = iCursor; iChar < +29; iChar++)
        {
          lcd.print(LargeText[iChar]);
          }}
          else
          {
            for(int iChar=iCursor; iChar<(iLenofLargeText - 1); iChar++)
            {
              lcd.print(LargeText[iChar]);
              }
              for (int iChar = 0; iChar <=29 -(iLenofLargeText - iCursor); iChar++)
              {
                lcd.print(LargeText[iChar]);
                }
                }
                iCursor++;
                }
# SIMULATION IN PROTEUS
 ![image](https://user-images.githubusercontent.com/104151424/165169534-3e3f4a31-02f8-494b-834e-e00f88a20a4a.png)

# FRITZING DIAGRAM
![image](https://user-images.githubusercontent.com/104151424/165169568-c6d3f421-de65-4dc9-ba69-8ab6520a19e0.png)
 
# Uploaded by:  Dufatanye Valens and Thomas Sankara
