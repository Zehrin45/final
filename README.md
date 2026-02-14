Perfect! I'll fill out the complete Tink-Her-Hack template for your Vesper project!

Vesper 🌸
Basic Details
Team Name: Vertex
Team Members

Member 1: Fathima Zehrin - Ilahia College of Engineering and Technology
Member 2: Mehrunisa Basheer - Ilahia College of Engineering and Technology


Project Description:-

Vesper is a smart safety jewelry web application featuring a cute Stardew Valley-inspired interface. Women can manage emergency contacts, simulate charm connection, and test emergency alerts through an adorable pixel-art aesthetic with floating lilies and bunny decorations. One button press would alert all contacts and authorities with GPS location.
The Problem statement
Women face constant safety threats - 1 in 3 women worldwide experience violence, yet existing safety solutions are either bulky panic buttons or smartphone apps requiring multiple steps. Real cases like Sarah Everard (2021) and Gabby Petito (2021) highlight the urgent need for instant, discreet emergency communication that women will actually wear daily.
The Solution
Vesper provides a web demo of fashionable safety jewelry with hidden emergency buttons. The app allows users to manage up to 5 emergency contacts through an intuitive interface. In production, one charm button press would instantly alert all contacts via call/SMS, notify police with GPS coordinates, and start optional recording - all within 3 seconds. This demo showcases the user experience with a friendly, pixel-art aesthetic that makes safety technology feel approachable rather than alarming.

Technical Details
Technologies/Components Used
For Software:
Languages used:

HTML5
CSS3
JavaScript (ES6+)

Frameworks used:

None (Vanilla JavaScript for lightweight performance)

Libraries used:

Google Fonts API (DotGothic16, Quicksand fonts)
LocalStorage API (Browser-native data persistence)

Tools used:

VS Code 
Chrome DevTools
Git & GitHub 
Browser APIs


Implementation
For Software:
Installation
bash# No installation required - it's a web app!
# Simply download the HTML file or visit the hosted URL

# Using VS Code Live Server extension
# Right-click HTML file → "Open with Live Server"
Run
# Double-click the HTML file - opens in your default browser


## Project Documentation
### For Software:

#### Screenshots (Add at least 3)
![Screenshot1]
<img width="548" height="412" alt="image" src="https://github.com/user-attachments/assets/08f0ba75-a625-4bd7-982c-ec6e9c496ff2" />

*Home screen showing connection status with animated floating lilies and bunny decorations. Status card displays heart icons and connection toggle button. Menu grid shows 4 options: Contacts (showing 0/5 friends), Emergency SOS button (red, glowing), Settings, and Location. Info box at bottom provides user guidance. The pink/beige Stardew Valley aesthetic creates a friendly, approachable safety interface.*

![Screenshot2]
<img width="395" height="433" alt="image" src="https://github.com/user-attachments/assets/f0ebf7d3-1753-4a1a-85f5-db317223672f" />

*Contacts management screen with "Add Friend" input card featuring fields for name, phone number, and relationship. Current contact list displays "~ friends (2/5) ~" with existing contacts shown as white cards containing flower emoji, contact name, phone number, relationship, and a removable [x] button. Empty state shows bunny emoji with cute message "no friends yet ~ add someone you trust <3".*

![Screenshot3]
<img width="366" height="443" alt="image" src="https://github.com/user-attachments/assets/9ac2633d-7357-4fc2-b220-9edf3f055860" />

*Emergency SOS confirmation dialog showing activation screen with "!! EMERGENCY !!" header. Message displays "* alert everyone? *" with listed actions: "<3 call contacts", "[!] alert police", "[x] share location". Cancel and Activate buttons present. Success screen shows all alerted contacts: "🌸 Mom (+1234567890)", "[!] police notified", "[x] location shared", ending with "stay safe! <3".*


#### Diagrams

**System Architecture & Workflow:**
```
┌─────────────────────────────────────────────────────────────┐
│                        USER OPENS APP                        │
└────────────────────┬────────────────────────────────────────┘
                     ↓
              ┌──────────────┐
              │ Browser Loads│
              │  HTML/CSS/JS │
              │ Google Fonts │
              └──────┬───────┘
                     ↓
         ┌───────────────────────┐
         │  Load from LocalStorage│
         │  • Emergency Contacts │
         │  • Previous State     │
         └───────────┬───────────┘
                     ↓
         ┌───────────────────────┐
         │   HOME SCREEN RENDER  │
         │  ┌─────────────────┐  │
         │  │  Status Card    │  │
         │  │ • Not Connected │  │
         │  │ • Connect Button│  │
         │  └─────────────────┘  │
         │  ┌─────────────────┐  │
         │  │   Menu Grid     │  │
         │  │ • Contacts 🐰   │  │
         │  │ • SOS ⚠️        │  │
         │  │ • Settings ⚙️   │  │
         │  │ • Location 📍   │  │
         │  └─────────────────┘  │
         │  • Floating Lilies 🌸│
         │  • Bunny Decorations🐰│
         └───────────┬───────────┘
                     ↓
    ┌────────────────┴────────────────┐
    │                                 │
┌───▼───────────┐           ┌─────────▼─────────┐
│USER CLICKS:   │           │ USER CLICKS:      │
│"Connect Charm"│           │ "Contacts" 🐰     │
└───┬───────────┘           └─────────┬─────────┘
    ↓                                 ↓
┌───────────────────┐       ┌──────────────────────┐
│toggleConnection() │       │  CONTACTS SCREEN     │
│• isConnected=true │       │ ┌─────────────────┐  │
│• Update UI        │       │ │ Add Friend Form │  │
│• Enable SOS       │       │ │ • Name          │  │
│• Show alert       │       │ │ • Phone         │  │
└───────┬───────────┘       │ │ • Relationship  │  │
        ↓                   │ │ [+] add [+]     │  │
   ┌─────────┐              │ └────────┬────────┘  │
   │Connected│              │          ↓            │
   │Status ✓ │              │   addContact()        │
   └────┬────┘              │   • Validate input    │
        │                   │   • Check limit (5)   │
        │                   │   • Save to array     │
        ↓                   │   • localStorage.save │
┌────────────────┐          │   • Update UI         │
│ SOS NOW ACTIVE │          │          ↓            │
└───────┬────────┘          │  ┌──────────────────┐ │
        ↓                   │  │ Contact List     │ │
   USER CLICKS              │  │ 🌸 Contact 1     │ │
   "!! SOS !!"              │  │ 📞 +123456789    │ │
        ↓                   │  │ ~ Mother         │ │
┌──────────────────┐        │  │    [x] Remove    │ │
│simulateEmergency()│        │  └──────────────────┘ │
│• Check connected  │        └──────────────────────┘
│• Check contacts   │                 │
│• Show confirm     │                 ↓
└────┬─────────────┘          Save to LocalStorage
     ↓                         (Persists on refresh)
┌─────────────────────────┐
│  CONFIRMATION DIALOG    │
│ "!! EMERGENCY !!"       │
│ "* alert everyone? *"   │
│                         │
│ <3 call contacts        │
│ [!] alert police        │
│ [x] share location      │
│                         │
│ [Cancel] [ACTIVATE]     │
└────┬────────────────────┘
     ↓ User Confirms
┌──────────────────────────┐
│   EMERGENCY ACTIVATED    │
│                          │
│  Display Success Alert:  │
│  ✿ Alert Sent! ✿        │
│                          │
│  🌸 Mom (+1234567890)    │
│  🌸 Dad (+9876543210)    │
│  🌸 Sister (+5555555555) │
│                          │
│  [!] police notified     │
│  [x] location shared     │
│                          │
│  stay safe! <3           │
└──────────────────────────┘
Caption: This diagram shows the complete user flow from opening the app through emergency activation. The app uses vanilla JavaScript for state management and LocalStorage for data persistence. Users can toggle connection status, manage up to 5 emergency contacts, and simulate emergency alerts. All data is stored locally in the browser, making this a fully functional offline-capable demo of the Vesper safety jewelry concept.

Key Components:

Presentation Layer: Single HTML file with embedded CSS/JS
State Management: JavaScript variables
Data Persistence: Browser LocalStorage API
User Interface: Three screens (Home, Contacts, Settings) with smooth navigation


Project Demo
Video
[Add your demo video link here - YouTube, Google Drive, etc.]
Video demonstrates:

Opening the web app and seeing the cute Stardew Valley aesthetic
Home screen with floating lilies and bunny decorations
Connecting the "charm" (toggling connection status)
Navigating to Contacts screen
Adding emergency contacts (name, phone, relationship)
Viewing contact list with flower emojis
Removing a contact with confirmation
Returning to home screen
Activating Emergency SOS button
Seeing confirmation dialog with all listed actions
Success message showing all alerted contacts and police notification
Exploring Settings screen with various options
Demonstrating that contacts persist after page refresh (LocalStorage)
Showcasing responsive design on different screen sizes
