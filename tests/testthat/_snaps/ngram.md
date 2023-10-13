# ngram works with varrying number of `n`

    Code
      cpp11_ngram(test_data, n = 0L, n_min = 0L, delim = "_")
    Condition
      Error:
      ! n must be a positive integer.

---

    Code
      cpp11_ngram(test_data, n = -1L, n_min = -1L, delim = "_")
    Condition
      Error:
      ! n must be a positive integer.

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
      * ngramming for: <none>

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
      * ngramming for: <none> | Trained

# printing

    Code
      print(rec)
    Message
      
      -- Recipe ----------------------------------------------------------------------
      
      -- Inputs 
      Number of variables by role
      predictor: 1
      
      -- Operations 
      * Tokenization for: text
      * ngramming for: text

---

    Code
      prep(rec)
    Message
      
      -- Recipe ----------------------------------------------------------------------
      
      -- Inputs 
      Number of variables by role
      predictor: 1
      
      -- Training information 
      Training data contained 2 data points and no incomplete rows.
      
      -- Operations 
      * Tokenization for: text | Trained
      * ngramming for: text | Trained

