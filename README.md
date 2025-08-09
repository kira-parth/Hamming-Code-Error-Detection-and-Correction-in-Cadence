# Hamming-Code-Error-Detection-and-Correction-in-Cadence
• Designed and simulated a Hamming (7,4) encoder and decoder system using Cadence Virtuoso to detect and correct single-bit errors in digital data streams. • Implemented syndrome-based error correction using custom logic gates (XOR, AND) and a 3x8 decoder, validating functionality through waveform simulation and block-level integration.
Process Overview 

1.Input Setup: 

The 7-bit data stream consists of: 

   * 4 Message Bits (D1,D2,D3,D4​). 

   * 3 Parity Bits (P1,P2,P4​). 

2. Parity Generation: 

     Parity bits are calculated from the message bits using 3-input XOR gates as follows: 

     1. P1=D1⊕D2⊕D4 

     2.P2=D1⊕D3⊕D4 

     3.P4=D2⊕D3⊕D4 

     These parity bits ensure error detection and correction during data transmission. 

3. Parity Comparison: 

   During transmission, the received data includes 4 message bits and 3 parity bits. 

   Using 2-input XOR gates, the system compares the received parity bits with recalculated parity bits to generate the syndrome vector (S1,S2,S4S_1, S_2, S_4S1​,S2​,S4​). 

4.Error Detection with Decoder: 

   The 3x8 Decoder takes the syndrome vector as input and outputs a one-hot signal to indicate the error location in the 7-bit stream. 

 

5.Error Correction: 

  Using XOR gates, the system flips the erroneous bit based on the one-hot signal from the decoder. 

  The corrected 7-bit stream is then used to extract the original 4-bit message. 

6.Output Recovery: 

  The corrected 7-bit stream is split into 4 message bits p1p2d1p3d2d3d4 
