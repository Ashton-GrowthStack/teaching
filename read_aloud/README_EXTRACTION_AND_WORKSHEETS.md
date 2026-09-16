# What Do You Like? - Extraction & Worksheets

## 🎯 Overview
This folder contains extracted phrases from the PowerPoint presentation and creative worksheets/flashcard activities for the K3 ESL "What do you like?" unit. These materials support **Chinese-style memorization** with choral repetition, gestures, and speed drills.

**Duration:** 2 × 20-minute sessions (40 minutes total)

---

## 📋 Files in This Folder

### 1. **EXTRACTED_PHRASES.txt**
- Text file with all extracted phrases from the PPTX
- Lists question patterns, food responses, and source reference
- **Use for:** Quick reference while planning lessons

### 2. **what_do_you_like_flashcards.html**
- Full flashcard worksheet with all 18 target phrases
- Organized into 2 sessions matching your lesson plan
- **Session 1:** Question phrases + basic responses
- **Session 2:** Food vocabulary + speed recall games
- **Use for:** Large display/board or printed worksheet

### 3. **what_do_you_like_cutout_flashcards.html**
- Printable flashcards ready to cut and use
- 3 pages with gesture/rhythm guide
- Each card has dashed borders for easy cutting
- Includes emoji for visual recognition
- **Use for:** Handheld practice during choral drills

### 4. **what_do_you_like_practice_worksheet.html**
- Interactive worksheet for individual students
- 5 activities: fill-in-the-blank, matching, write-your-own, true/false, choral repeat
- Includes word bank and space for student responses
- **Use for:** Homework or in-class individual practice

---

## 🎓 How to Use These Materials

### LESSON 1: QUESTION PHRASES (20 minutes)
**Goal:** Students learn to ask "What do you like for...?"

1. **Warm-up (2 min):** Choral repeat the 6 question phrases
2. **Gesture Anchors (5 min):** Assign gestures to each meal time
3. **Speed Drill (8 min):** Three rounds of increasing speed
   - Round 1: Slow, clear pronunciation
   - Round 2: Normal speed
   - Round 3: Fast (30 seconds for all 6 phrases)
4. **Response Introduction (5 min):** Learn 6 basic food responses

### LESSON 2: FOOD VOCABULARY (20 minutes)
**Goal:** Practice food words with speed recall games

1. **Warm-up (2 min):** Recap question phrases from Lesson 1
2. **Call & Response Game (6 min):**
   - Teacher asks: "What do you like for breakfast?"
   - Students respond with food words from the card
3. **Speed Drill - Food Words (7 min):**
   - Show flashcard 3 seconds
   - Students call out the word
   - Increase speed with each round
4. **Chain Drill (5 min):** Point to students, they complete: "I like..."

---

## 🔄 Extraction Method (For Future Use)

### How These Phrases Were Extracted

The PPTX file contains embedded text that was extracted using Python's `zipfile` and XML parsing:

```bash
# The command used to extract:
python3 << 'EOF'
import zipfile
import xml.etree.ElementTree as ET

pptx_path = "/path/to/file.pptx"
with zipfile.ZipFile(pptx_path, 'r') as zip_ref:
    for file in sorted(zip_ref.namelist()):
        if file.startswith('ppt/slides/slide') and file.endswith('.xml'):
            with zip_ref.open(file) as f:
                xml_content = f.read().decode('utf-8')
                ns = {'a': 'http://schemas.openxmlformats.org/drawingml/2006/main'}
                root = ET.fromstring(xml_content)
                for t in root.findall('.//a:t', ns):
                    if t.text and t.text.strip():
                        print(t.text)
EOF
```

### Why This Method Works
- ✅ **PPTX/DOCX are ZIP files** - they contain XML text inside
- ✅ **No special software needed** - just Python's built-in libraries
- ✅ **Preserves formatting** - extracts actual text, not OCR
- ✅ **Repeatable** - same method works for any PPTX file

### To Extract from Other Files

1. **For PPTX files:** Use the Python method above
2. **For DOCX files:** Change to `from docx import Document` (requires python-docx)
3. **For PDFs:** Use `pdftotext` command-line tool or python-pdf libraries

---

## 📊 The 18 Target Phrases

### Question Patterns (6)
1. What do you like for breakfast?
2. What do you like for snack?
3. What do you like for lunch?
4. What do you like for tea?
5. What do you like for dinner?
6. What do you like at bedtime?

### Food Responses (12)
- **Breakfast:** cereal, toast, yoghurt, egg
- **Lunch/Dinner:** sandwich, pizza, potato, pasta, apple, cake
- **Bedtime/Tea:** banana, biscuit, milk, chocolate

---

## 🎭 Gesture & Memorization Tips

### Breakfast Foods - SLOW & SMOOTH
- 🥣 **Cereal** - Circle hand motion (pouring)
- 🍞 **Toast** - Pop hand up
- 🥛 **Yoghurt** - Spoon motion
- 🥚 **Egg** - Crack hand gesture

### Lunch & Dinner - MEDIUM SPEED
- 🍎 **Apple** - Pick motion
- 🥪 **Sandwich** - Clap hands together
- 🍕 **Pizza** - Triangle hand shape
- 🥔 **Potato** - Hold up fist
- 🍝 **Pasta** - Twirl fork motion

### Bedtime Foods - SOFT & GENTLE
- 🍌 **Banana** - Peel motion
- 🍪 **Biscuit** - Bite motion
- 🥛 **Milk** - Cup hands
- 🍫 **Chocolate** - Rubbing hands together

---

## 📁 Source Files
**Original PPTX:** `/Users/ashton/Claude Projects/teaching/phonics/K3 fall semster /Unit 1-Health/1-What do you like/3-What do you like (Anna owen, food, health).pptx`

**Extraction Date:** 2026-09-16

---

## 💡 Tips for Success
- **Repetition is key** - Use speed drills to build automaticity
- **Gestures stick** - Physical anchors help memory retention
- **Group energy** - Choral drills maintain engagement for K3 students
- **Mix & match** - Combine phrases to create questions students can answer
- **Practice daily** - 10 minutes daily beats one long session

---

## 🚀 Next Steps
1. Print the flashcard worksheets
2. Cut out individual flashcards for classroom use
3. Practice gestures with your students
4. Use the worksheets for individual practice
5. Celebrate progress! 🌟

---

**Last Updated:** 2026-09-16  
**Method:** Automated PPTX XML text extraction  
**Status:** Ready for classroom use
