# custom extraction functions work works

    Code
      rec %>% step_textfeature(text, extract_functions = list(as.character)) %>% prep()
    Condition
      Error in `step_textfeature()`:
      Caused by error in `prep()`:
      ! Can't subset columns that don't exist.
      x Column `text` doesn't exist.

---

    Code
      rec %>% step_textfeature(text, extract_functions = list(function(x) 1)) %>%
        prep()
    Condition
      Error in `step_textfeature()`:
      Caused by error in `prep()`:
      ! Can't subset columns that don't exist.
      x Column `text` doesn't exist.

# check_name() is used

    Code
      prep(rec, training = dat)
    Condition
      Error in `step_textfeature()`:
      Caused by error in `bake()`:
      ! Name collision occurred. The following variable names already exist:
      * `textfeature_text_n_words`

# empty printing

    Code
      rec
    Message
      
      -- Recipe ----------------------------------------------------------------------
      
      -- Inputs 
      Number of variables by role
      outcome:    1
      predictor: 10
      
      -- Operations 
      * Text feature extraction for: <none>

---

    Code
      rec
    Message
      
      -- Recipe ----------------------------------------------------------------------
      
      -- Inputs 
      Number of variables by role
      outcome:    1
      predictor: 10
      
      -- Training information 
      Training data contained 32 data points and no incomplete rows.
      
      -- Operations 
      * Text feature extraction for: <none> | Trained

# keep_original_cols - can prep recipes with it missing

    Code
      rec <- prep(rec)
    Condition
      Warning:
      `keep_original_cols` was added to `step_tf()` after this recipe was created.
      i Regenerate your recipe to avoid this warning.

---

    Code
      rec <- prep(rec)
    Condition
      Warning:
      `keep_original_cols` was added to `step_textfeature()` after this recipe was created.
      i Regenerate your recipe to avoid this warning.

# printing

    Code
      print(rec)
    Message
      
      -- Recipe ----------------------------------------------------------------------
      
      -- Inputs 
      Number of variables by role
      predictor: 1
      
      -- Operations 
      * Text feature extraction for: text

---

    Code
      prep(rec)
    Message
      
      -- Recipe ----------------------------------------------------------------------
      
      -- Inputs 
      Number of variables by role
      predictor: 1
      
      -- Training information 
      Training data contained 4 data points and no incomplete rows.
      
      -- Operations 
      * Text feature extraction for: text | Trained

