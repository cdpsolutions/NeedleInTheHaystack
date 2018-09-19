# NeedleInTheHaystack
//CIS269 Programming Maintenance - Debug and refactor the broken program
//Christine Cullen Spring 2018
Finds the Index of a substring within a string

// findSubString
    // searches for a string (needle) within another string (haystack)
    // returns the first index position of the needle in the haystack,
    // or -1 if the needle is not found.
    private int findSubString(string haystack, string needle)
    {
        // if needle longer than haystack, can't be found
        if (needle.Length > haystack.Length) return -1;
     
        // for each step we check if the needle matches
        // the current position
        bool match = false;

        // loop variables
        int haystackIndex, needleIndex;//changed variable names from i,j to user friendly names

        // consider all start positions in the haystack
        for (haystackIndex = 0; haystackIndex <= haystack.Length - needle.Length; haystackIndex++)//corrected all start positions include 0
        {
            // for each start position, assume the needle matches
            match = true;

            // consider each position in the needle, relative to
            // the current position in the haystack
            for (needleIndex = 0; needleIndex < needle.Length; needleIndex++)
            {
                // if they don't match, then cancel the match
                if (haystack[haystackIndex + needleIndex] != needle[needleIndex])//checks from 0 to the size of the needle to where you are starting on your haystack
                    match = false;//break into two lines for debugging the breakpoint wasn't working
            }

            // if all position in the needle match the haystack
            // return the current position
            if (match) return haystackIndex;//j returned index at the end of the needle.
            //haystackIndex moves with the needle
        }
        
        return -1; //was 0
    } 
