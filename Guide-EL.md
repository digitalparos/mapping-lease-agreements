# beach-contracts-mapping guide _(αγγλική έκδοση)_  

**Πώς να οπτικοποιήσετε τις περιοχές μίσθωσης που βρήκατε στα συμβόλαια μίσθωσης μέσω του [diavgeia.gov.gr](https://diavgeia.gov.gr/) σε χάρτη της Google.**

---

Βρήκατε λοιπόν τη σύμβαση για ένα μέρος που υποπτεύεστε ότι παραβιάζει τη συμφωνία μίσθωσης. Ακολουθεί ένας εύκολος οδηγός για το πώς να σχεδιάσετε έναν χάρτη χρησιμοποιώντας τις συντεταγμένες που θα βρείτε μέσα στη σύμβαση. Θα χρειαστείτε μόνο ένα πρόγραμμα επεξεργασίας κειμένου και μια σύνδεση στο διαδίκτυο.

### Προετοιμασία του Αρχείου
Θα βρείτε έναν φάκελο "files" με συνοδευτικά αρχεία πιο πάνω σε αυτή τη σελίδα. Ανοίξτε το αρχείο που ονομάζεται `empty.geojson` με ένα πρόγραμμα επεξεργασίας κειμένου. Εάν χρησιμοποιείτε ένα πρόγραμμα όπως το WordPad ή το Word, είναι καλύτερο να τα επιλέξετε Όλα και να αλλάξετε τη γραμματοσειρά σε μια οικογένεια σταθερού πλάτους, όπως η "Courier", η οποία είναι συνήθως διαθέσιμη σε Windows και MacOS, ώστε να διευκολυνθείτε στη διαδικασία επεξεργασίας.

**[01_data-extraction.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/01_data-extraction.jpg?raw=true)**  
Έτσι πρέπει να φαίνεται το αρχείο `empty.geojson`. Στις σειρές 3 και 14 έχω αλλάξει τις καταχωρήσεις "name" σε "Paros on the rocks" καθώς αυτό είναι το μισθωτήριο συμβόλαιο που θα χρησιμοποιήσω για αυτό το παράδειγμα.

**[02_data-extraction.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/02_data-extraction.jpg?raw=true)**  
Εδώ μπορείτε να δείτε την επιλεγμένη ενότητα που ορίζει μια περιοχή πολυγώνου στο χάρτη που θα δημιουργήσετε. Εάν τα συμβόλαια περιλαμβάνουν περισσότερα από ένα τμήματα/πολύγωνα ανατρέξτε στο (05_data-extraction.jpg).

### Επεξεργασία Συντεταγμένων
**[03_data-extraction.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/03_data-extraction.jpg?raw=true)**  
Τώρα, ανοίξτε το αρχείο pdf της σύμβασης μίσθωσης και βρείτε την ενότητα που περιγράφει την περιοχή μίσθωσης. Συνήθως ξεκινά με τετραγωνικά μέτρα και ακολουθούν μπλοκ συντεταγμένων X και Y. Αντιγράψτε την πρώτη συντεταγμένη X, στο παράδειγμά μας, `607718.65`, και επικολλήστε την στο αρχείο `empty.geojson`, όπου έβαλα ένα σύμβολο κράτησης θέσης "X-COORD". Επαναλάβετε το ίδιο με την πρώτη συντεταγμένη Υ, στο παράδειγμά μας `4109623.16`, και τοποθετήστε την εκεί που βρίσκεται το σύμβολο κράτησης θέσης "Y-COORD". Συνεχίστε μέχρι να τελειώσετε με τα μπλοκ συντεταγμένων. Εάν εξαντληθούν τα σύμβολα κράτησης θέσης αλλά εσείς έχετε κι άλλα σημεία, αντιγράψτε/επικολλήστε μία ενότητα 
```
[
    X-COORD,
    Y-COORD
],
[
    X-COORD,
    Y-COORD
]
```
χωρίς να ξεχάσετε το κόμμα για να διαχωρίσετε τα ζεύγη συντεταγμένων που περικλείονται σε αγκύλες.
**ΣΗΜΑΝΤΙΚΟ:** Όταν τελειώσετε, αντιγράψτε το πρώτο ζεύγος συντεταγμένων και επικολλήστε το στο τέλος όλων των ζευγών συντεταγμένων για να κλείσετε σωστά το Πολύγωνο.

**[04_data-extraction.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/04_data-extraction.jpg?raw=true)**  
Έτσι πρέπει να φαίνεται το αρχείο geojson στο παράδειγμά μας. Μπορείτε να το αποθηκεύσετε ως νέο αρχείο. Το ονόμασα "paros-on-the-rocks-2100.geojson". Η κατάληξη _-2100_ τονίζει ότι το σύστημα συντεταγμένων των δεδομένων είναι το EPSG:2100, που χρησιμοποιείται συνήθως στην Ελλάδα.

**[05_data-extraction.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/05_data-extraction.jpg?raw=true)**  
Εάν υπάρχουν περισσότερες από μία περιοχές στη σύμβαση μίσθωσης, μπορούν να προστεθούν πολλαπλές περιοχές στο αρχείο geojson. Αντιγράψτε το τμήμα που περικλείεται με αγκύλες μέσα στο μπλοκ "features" για να λειτουργήσει.

### Μετατροπή Δεδομένων
**[06_data-conversion.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/06_data-conversion.jpg?raw=true)**  
Επισκεφθείτε τον ιστότοπο [MyGeodata Cloud](https://mygeodata.cloud/). Για να κάνετε μετατροπή περισσότερες από 3 φορές, δημιουργήστε έναν δωρεάν λογαριασμό κάνοντας κλικ στο "Sign In" στην κύρια σελίδα.

**[07_data-conversion.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/07_data-conversion.jpg?raw=true)**  
Αφού συνδεθείτε, κάντε κλικ στο "Go to Converter >>".

**[08_data-conversion.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/08_data-conversion.jpg?raw=true)**  
Κάντε κλικ στο "Or browse files to convert" και επιλέξτε το αρχείο geojson που επεξεργαστήκατε, "paros-on-the-rocks-2100.geojson" στο παράδειγμά μας.

**[09_data-conversion.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/09_data-conversion.jpg?raw=true)**  
Αυτή η οθόνη δείχνει ότι το αρχείο έχει μεταφορτωθεί και είναι έτοιμο για μετατροπή. Κάντε κλικ στο "Continue".

**[10_data-conversion.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/10_data-conversion.jpg?raw=true)**  
Μπορείτε να ελέγξετε ότι όλα λειτούργησαν αναζητώντας το όνομα που επιλέξατε στο πλαίσιο κειμένου "Input Layers to Convert". Επίσης, στην ενότητα “Input parameters” θα πρέπει να αναφέρεται σωστά το σύστημα συντεταγμένων του Greek Grid. Κάντε κλικ στο "Show in a Map" για να επαληθεύσετε ότι όλες οι συντεταγμένες είναι σωστές.

**[11_data-conversion.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/11_data-conversion.jpg?raw=true)**  
Εάν όλα πήγαν καλά, η περιοχή εμφανίζεται στον χάρτη στην αναμενόμενη τοποθεσία.

**[12_data-conversion.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/12_data-conversion.jpg?raw=true)**  
Επιλέξτε "KML" ως μορφή εξόδου και "WGS 84 (EPSG:4326)" ως σύστημα συντεταγμένων. Επιλέξτε το "name" στις αναθέσεις πεδίων για να μεταφέρετε τα ονόματα στο αρχείο KML. Κάντε κλικ στο "Convert now!"

**[13_data-conversion.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/13_data-conversion.jpg?raw=true)**  
Η μετατροπή θα πρέπει να είναι επιτυχής. Κάντε κλικ στο "Download" για να αποθηκεύσετε το αρχείο KML.

### Δημιουργία του χάρτη
**[14_map-creation.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/14_map-creation.jpg?raw=true)**  
Επισκεφτείτε τους [Χάρτες Google](https://www.google.com/maps) και κάντε κλικ στο εικονίδιο "Αποθηκευμένο" στην αριστερή πλαϊνή γραμμή. Επιλέξτε την καρτέλα "Χάρτες" και, στη συνέχεια, κάντε κλικ στο "Άνοιγμα των Χαρτών μου".

**[15_map-creation.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/15_map-creation.jpg?raw=true)**  
Κάντε κλικ στο "+ ΔΗΜΙΟΥΡΓΙΑ ΝΕΟΥ ΧΑΡΤΗ".

**[16_map-creation.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/16_map-creation.jpg?raw=true)**  
Τώρα είστε έτοιμοι να εισαγάγετε τα δεδομένα KML. Μπορεί να θέλετε να αλλάξετε τον "Χάρτη βάσης" σε δορυφορικά δεδομένα.

**[17_map-creation.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/17_map-creation.jpg?raw=true)**  
Κάντε κλικ στο σύνδεσμο "εισαγωγή".

**[18_map-creation.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/18_map-creation.jpg?raw=true)**  
Επιλέξτε ή σύρετε το αρχείο KML που αποθηκεύσατε στο παράθυρο.

**[19_map-creation.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/19_map-creation.jpg?raw=true)**  
Θα πρέπει να εμφανιστεί το επίπεδο που δημιουργήθηκε πρόσφατα και ο χάρτης θα πρέπει να μεγεθύνεται στην έκτασή του.

**[20_map-creation.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/20_map-creation.jpg?raw=true)**  
Μπορείτε να προσαρμόσετε την εμφάνιση του επιπέδου επιλέγοντας χρώμα γεμίσματος, διαφάνεια και πλάτος περιγράμματος.

**[21_map-creation.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/21_map-creation.jpg?raw=true)**  
Ονομάστε τον χάρτη σας κάνοντας κλικ στον τίτλο.

**[22_map-creation.jpg](https://github.com/digitalparos/lease-agreements-mapping/blob/3136f2311e0ac37f1b9a893044da7ce69ca5c396/step-by-step-jpgs/22_map-creation.jpg?raw=true)**  
Κάντε κλικ στο "Κοινή χρήση" για να ανοίξετε τις Επιλογές Κοινή Χρήση Χάρτη. Αντιγράψτε τη μοναδική διεύθυνση URL και κοινοποιήστε την, διασφαλίζοντας ότι έχει επιλεγεί η επιλογή "Όποιος έχει αυτόν τον σύνδεσμο μπορεί να προβάλει".

### ΣΗΜΕΙΩΣΕΙΣ
- Τις περισσότερες φορές, οι συντεταγμένες περιλαμβάνουν τυπογραφικά λάθη. Που σημαίνει ότι είτε λείπει ένας αριθμός ή είναι πιο πολλοί από ό,τι πρέπει. Εξαιτίας αυτού η περιοχή μπορεί να  εμφανιστεί παραμορφωμένη, καθώς συνήθως κάποια συντεταγμένη δεν είναι στη θέση της. Δεδομένου ότι το σύστημα είναι σε μέτρα, με λίγη προσεκτική εξέταση θα πρέπει να μπορείτε να καταλάβετε τα σφάλματα. Αυτοί οι αριθμοί είναι απλώς συντεταγμένες X/Y σε μέτρα, και ο χάρτης που αναζητάτε βρίσκεται στην Ελλάδα. [Μπορείτε να ανατρέξετε σε αυτόν τον ιστότοπο για περισσότερες εξηγήσεις.](https://epsg.io/2100)
- Μην ξεχάσετε να αντιγράψετε το πρώτο ζεύγος συντεταγμένων και να το επικολλήσετε στο τέλος όλων των ζευγών συντεταγμένων για να κλείσετε σωστά το Πολύγωνο.
