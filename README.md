# readcsv



from tkinter.filedialog import askopenfilename, asksaveasfilename


def main():
    print("This program creates a file of usernames from a ")
    print("file of names.")

    # get the file names
    infileName = askopenfilename()
    outfileName = asksaveasfilename()

    # open the files
    infile = open(infileName, "r")
    outfile = open(outfileName, "w")

    # process each line of the input file
    for line in infile:
        # get first and last names form line
        first, last = line.split()

        # create the username
        uname = (first[0] + last[:7]).lower()

        # write it to the output file
        print(uname, file = outfile)

    # close both files
    infile.close()
    outfile.close()

main()
