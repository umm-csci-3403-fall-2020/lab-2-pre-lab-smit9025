# Leak report

We can tell that calloc is used only in strip, which then spits a result that goes into is_clean, which then leads up to main. Free() is never used once within the code to free up the used memory. We can use free(cleaned) at the end of is_clean to free the used memory that is stored in cleaned.
