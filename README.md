# DNA-to-Protein
This is a simple Python script that translates a DNA sequence into a protein (amino acid sequence) using the standard genetic code. 

genetic_code = {
    'ATA':'I', 'ATC':'I', 'ATT':'I', 'ATG':'M',
    'ACA':'T', 'ACC':'T', 'ACG':'T', 'ACT':'T',
    'AAC':'N', 'AAT':'N', 'AAA':'K', 'AAG':'K',
    'AGC':'S', 'AGT':'S', 'AGA':'R', 'AGG':'R',
    'CTA':'L', 'CTC':'L', 'CTG':'L', 'CTT':'L',
    'CCA':'P', 'CCC':'P', 'CCG':'P', 'CCT':'P',
    'CAC':'H', 'CAT':'H', 'CAA':'Q', 'CAG':'Q',
    'CGA':'R', 'CGC':'R', 'CGG':'R', 'CGT':'R',
    'GTA':'V', 'GTC':'V', 'GTG':'V', 'GTT':'V',
    'GCA':'A', 'GCC':'A', 'GCG':'A', 'GCT':'A',
    'GAC':'D', 'GAT':'D', 'GAA':'E', 'GAG':'E',
    'GGA':'G', 'GGC':'G', 'GGG':'G', 'GGT':'G',
    'TCA':'S', 'TCC':'S', 'TCG':'S', 'TCT':'S',
    'TTC':'F', 'TTT':'F', 'TTA':'L', 'TTG':'L',
    'TAC':'Y', 'TAT':'Y', 'TAA':'_', 'TAG':'_', 'TGA':'_'
}

def translate_dna_to_protein(dna_sequence):
    dna_sequence = dna_sequence.upper().replace(" ", "").replace("\n", "")
    protein = ""

    if len(dna_sequence) % 3 != 0:
        print("Warning: the length of the DNA sequence is not a multiple of 3. The last codon will be discarded.")

    for i in range(0, len(dna_sequence) - 2, 3):
        codon = dna_sequence[i:i+3]
        amino_acid = genetic_code.get(codon, '?')
        protein += amino_acid

    return protein

if __name__ == "__main__":
    dna_input = input("What is your DNA sequence? ")
    protein_output = translate_dna_to_protein(dna_input)
    print("Translate to Protein: ", protein_output)
