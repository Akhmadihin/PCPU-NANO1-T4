# PCPU-NANO1-T4
PCPU-NANO1 T4 — a 1-bit CPU built with 4 BC547 transistors and 7 1kΩ resistors. Implements NOP and NADJZ instructions. Logic: OUT = NAND(DATA,IN); JMP = INS &amp; DATA &amp; IN. Scales to n bits by connecting cores in parallel. Ideal for learning CPU architecture.
