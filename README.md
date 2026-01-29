![Arduino](https://img.shields.io/badge/Platform-Arduino-blue)
![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)

# Smart Pole – Be Smart and Safe

Smart Pole is a final-year Diploma project focused on enhancing public safety by integrating emergency response mechanisms into urban street lighting infrastructure.

## Project Overview

The Smart Pole system upgrades conventional streetlights with emergency alert features. It enables individuals in distress—particularly women, children, and the elderly—to trigger an immediate alert that notifies nearby authorities while activating visual and audio indicators at the location.

## Aim

To design and implement a real-time emergency alert system embedded into smart street poles with the following functionalities:

- Emergency button activation  
- Audio and visual alerts (buzzer and LED)  
- Real-time GPS location tracking  
- GSM-based SMS notification to authorities  

## Components Used

### Hardware
- Arduino Uno (Microcontroller)
- GPS Module (SIM28ML or equivalent)
- GSM Module (SIM900A)
- Buzzer
- LED Indicator (Red)
- Emergency Push Button
- 12V 2A Power Adapter
- Data Transfer Cable

### Software
- Arduino IDE
- MS Word (Documentation)
- Web Browsers for testing and monitoring

## System Workflow

1. Emergency button is pressed  
2. Buzzer and LED indicator are activated  
3. GPS module captures the real-time location  
4. GSM module sends an alert message with GPS coordinates  
5. Authorities receive the alert and initiate response  

## Project Structure

- `/code/` – Arduino source code  
- `/docs/` – Project documentation and reports  
- `/output-images/` – Output screenshots  
- `/Models/` – System and architecture design diagrams  

## Key Features

- Immediate visual and audible alert system  
- Real-time GPS-based location sharing  
- Implemented using Embedded C on Arduino  
- Automated SMS alert dispatch  
- Extendable architecture for future integrations  

## Use Cases

- Enhancing women’s safety in urban and public areas  
- Emergency assistance for elderly individuals  
- Child safety in public locations  

## Output

- **SMS Alert:** Emergency message containing GPS coordinates  
- **LED Indicator:** Highlights the affected location  
- **Buzzer/Siren:** Alerts nearby individuals  

## Sample Code Snippet

```c
if (digitalRead(btnPin) == HIGH) {
  digitalWrite(ledPin, HIGH);
  delay(3000);
  digitalWrite(ledPin, LOW);
  sgsm.listen();
  sgsm.print("AT+CMGF=1\r");
  delay(1000);
  sgsm.print("AT+CMGS=\"+91XXXXXXXXXX\"\r");
  delay(1000);
  sgsm.print("https://www.google.com/maps/?q=");
  sgsm.print(gpslat, 6);
  sgsm.print(",");
  sgsm.print(gpslon, 6);
  delay(1000);
  sgsm.write(0x1A);
}
## Future Enhancements

- Integration of camera modules for visual monitoring  
- Cloud-based data storage and analytics  
- Mobile application interface for public access  
- Solar-powered implementation for sustainability  

## Developed By

**Hemasri Bandari & Team**  
Diploma in Computer Engineering  
Government Polytechnic, Warangal (2021–2024)

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## References

- Arduino Documentation  
- W3Schools  
- Microcontrollers Lab – SIM900A Guide  
