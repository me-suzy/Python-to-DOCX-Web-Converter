# Python-to-DOCX Web Converter

## Descriere
Web-Convertor pentru transformarea codului Python în documente Word (.docx). Această aplicație web permite utilizatorilor să introducă cod Python care generează documente Word și să descarce rezultatul direct din browser.

## Caracteristici
- Interfață web simplă și intuitivă
- Introducere și editare cod Python
- Două modalități de conversie:
  - Salvare cod Python ca document Word (.docx)
  - Executare cod Python și descărcare rezultat generat
- Exemplu predefinit de cod pentru a facilita utilizarea
- Suport pentru formatare complexă a documentelor Word

## Tehnologii utilizate
- Python 3.x
- Flask (framework web)
- python-docx (generare documente Word)
- HTML, CSS și JavaScript (interfața utilizator)

## Cerințe
```
flask
python-docx
```

## Instalare și utilizare
1. Clonați acest repository
2. Instalați dependențele:
   ```
   pip install flask python-docx
   ```
3. Rulați aplicația:
   ```
   python app.py
   ```
4. Accesați aplicația în browser la adresa: http://127.0.0.1:5001  sau, alternativa, http://127.0.0.1:5000

## Structura proiectului
- `app.py` - Serverul Flask care gestionează rutele și execuția codului Python
- `templates/index.html` - Interfața web pentru introducerea și conversia codului

## Cum funcționează
1. Utilizatorul introduce cod Python în interfața web sau încarcă exemplul predefinit
2. Codul trebuie să utilizeze biblioteca python-docx pentru a genera un document Word
3. La apăsarea butonului "Execută codul și descarcă rezultatul", serverul execută codul Python
4. Documentul generat este trimis înapoi utilizatorului pentru descărcare

## Exemplu de cod
```python
from docx import Document
from docx.shared import Pt, RGBColor
from docx.enum.text import WD_ALIGN_PARAGRAPH

# Creăm un document nou
doc = Document()

# Adăugăm titlul
titlu = doc.add_heading('Exemplu de Document Simplu', level=0)
titlu.alignment = WD_ALIGN_PARAGRAPH.CENTER

# Adăugăm primul paragraf
p1 = doc.add_paragraph('Acesta este primul paragraf al documentului. ')
run1 = p1.add_run('Această parte este formatată diferit.')
run1.bold = True
run1.font.size = Pt(14)
run1.font.color.rgb = RGBColor(0, 0, 255)  # Albastru

# Adăugăm al doilea paragraf
p2 = doc.add_paragraph('Acesta este al doilea paragraf. ')
run2 = p2.add_run('Folosim un alt font aici.')
run2.italic = True
run2.font.name = 'Arial'
run2.font.size = Pt(12)
run2.font.color.rgb = RGBColor(255, 0, 0)  # Roșu

# Salvăm documentul
doc.save('document_simplu.docx')
```

## Notă de securitate
Această aplicație execută cod Python arbitrar pe server. Utilizați-o doar în medii sigure și controlate. Nu este recomandată expunerea acestei aplicații pe internet fără măsuri suplimentare de securitate.

## Contribuții
Contribuțiile sunt binevenite! Vă rugăm să creați un "fork" al acestui repository și să trimiteți un "pull request" cu îmbunătățirile propuse.

## Licență
Acest proiect este disponibil sub licența MIT. Consultați fișierul LICENSE pentru detalii.

---

*Notă: Această aplicație este concepută pentru uz educațional și demonstrativ. Nu este recomandată pentru medii de producție fără măsuri suplimentare de securitate.*
