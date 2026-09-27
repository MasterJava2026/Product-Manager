# Product-Manager
My first Python project: Product Manager  
speicher = []   

class Product:
    def __init__(self, ID, name, preis, menge):
        self.ID = ID
        self.name = name
        self.preis = preis
        self.menge = menge

    def __str__(self):
        return f"{self.ID} | {self.name} | {self.preis}€ | {self.menge} Stück"
    
    def set_name(self,new_name):
        self.name = new_name


def speichern(ID, name, preis, menge):
    werte = Product(ID, name, preis, menge)
    speicher.append(werte)
    print("Die Werte: " + str(werte))

while True:

    print("was nehmen Sie vor?")
    nummer = input("1. Produkt speichern\n2. Produkt anzeigen\n3. Produkt löschen\n4.Produkt ändern\n5. Programm beenden\n")

    
    if nummer == "1":
        while True:
            try:  
                ID = int(input("Geben Sie die ID des Produkts ein: \n"))
                break
            except ValueError:
                print("Ungültige Eingabe. Bitte geben Sie eine ganze Zahl ein.")
            
        name = input("Geben Sie den Namen des Produkts ein: \n")
        while True: 
            try:    
                preis = float(input("Geben Sie den Preis des Produkts ein: "))
                break
            except ValueError:
                print("Ungültige Eingabe. Bitte geben Sie eine Zahl ein.") 

        while True:
            try:    
                menge = int(input("Geben Sie die Menge des Produkts ein: "))
                break
            except ValueError:
                print("Ungültige Eingabe. Bitte geben Sie eine ganze Zahl ein.")

        speichern(ID, name, preis, menge)

    elif nummer == "2":
        for produkt in speicher:
            print(produkt)
    elif nummer == "3":
       name = input("geben Sie den Namen des Produkts ein, das Sie löschen möchten: \n");
       for produkt in speicher:
           if produkt.name == name:
               speicher.remove(produkt)
               print(f"Produkt {name} wurde gelöscht.")
               break

    elif nummer == "4":
        name = input("Was möchten Sie an dem Produkt ändern? Geben Sie den Namen ein \n")
        for produkt in speicher:
            if produkt.name == name:
                new = input("Der neue Name ")
                produkt.set_name(new)
                print(f"produkt: {produkt} wrude geändert")


    elif nummer == "5":
        print("Programm wird beendet. \n")
        break    




