# Leak report

The memory leaks happen after comparing the two strings with "results = strcmp(str, cleaned);"
My understanding is that it's stored for comparing, and then after it's checked to be claen or not, nothing is done to it in the memory, so therefore it continuously takes up memory.

How to fix this would be to free up the comparisoned string that's set to memory at the beginning of the function. "int is_cleaned(char* str) { char* cleaned; int result;", the problem being that cleaned is being stored, for comparison, but then not being freed after it's no longer needed. Simply putting "free(cleaned); before calling te result is how to fix this.  

