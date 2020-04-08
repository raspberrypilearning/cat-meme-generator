## Δημιουργία του meme

Χρειάζεται να δημιουργήσουμε μια περιοχή όπου θα εμφανίζεται το meme. Αυτή η περιοχή θα ξεκινήσει κενή, επειδή όταν αρχίσει η φόρτωση της σελίδας, δεν θα γνωρίζουμε ποια εικόνα ή κείμενο θέλει να χρησιμοποιήσει ο χρήστης.

- Κάτω από την ετικέτα ` </form>`, πρόσθεσε μια νέα γραμμή κώδικα:

  ```html
  <div id="meme_text">Εδώ μπαίνει το υπόδειγμα κειμένου</div>
  ```

  Αυτό είναι ένα αντικείμενο `<div>` - είναι ένα αόρατο κουτί στο οποίο θα τοποθετηθεί τελικά το κείμενο για το meme μας. Του έχουμε δώσει ένα `id` όπως ακριβώς κάναμε και στα πλαίσια εισαγωγής.

- Τώρα πρόσθεσε ακόμη ένα `<div>` κάτω από το προηγούμενο:

  ```html
    <div id="meme_picture"><img src="" height="500" width="600"></div>
    ```

    Μέσα σε αυτό το `<div>`, υπάρχει επίσης μια άλλη ετικέτα που εμφανίζει μια εικόνα. Το `src=""` υποδεικνύει ποια εικόνα θα εμφανιστεί. Σε αυτήν την περίπτωση, αφήσαμε την εικόνα κενή, επειδή δεν έχουμε ακόμα την εικόνα από το χρήστη.

- Αποθήκευσε και ανανέωσε. Η εικόνα θα είναι ένα κενό πλαίσιο και το κείμενο του παραδείγματος θα εμφανιστεί στην προεπιλεγμένη γραμματοσειρά, η οποία δεν θυμίζει και πολύ γραμματοσειρά για meme:

    ![Example text default font](images/example-text-default.png)

- If you're using a file on your computer, find the `<head>` section in your code and add this code between `<head>` and `</head>`. (Skip this step if you're using CodePen.)

  ```html
  <style type="text/css">
  </style>
  ```

- Paste the code below between the `<style>` tags to give your text a meme style. If you're using CodePen, paste it into the CSS section.

    ```css
    #meme_text {
        background-color: transparent;
        font-size: 40px;
        font-family: "Impact";
        color: white;
        text-shadow: black 0px 0px 10px;
        width: 600px;
        position: absolute;
        left: 15px;
        top: 400px;
    }
    ```

  The `left: 15px` and `top: 400px` lines determine how far the text is from the left and the top of the page. You can alter these numbers to make the text appear in a different place on your meme if you like. If you would like to know more about CSS styles, visit the [w3schools CSS reference](http://www.w3schools.com/CSSref/){:target="_blank"}.

  ![Example text in meme](images/example-text-memey.png)
