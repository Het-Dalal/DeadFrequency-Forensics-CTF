# Dead Frequencies — CTF Write-up

**Category:** Audio Analysis & XOR  
**Tools Used:** Sonic Visualiser, CyberChef

## Challenge Overview

This challenge provides two files: an encrypted file named `encrypted.bin` and an audio file named `signal.wav`.

The encrypted file contains unreadable characters when opened as ordinary text. The audio file contains a clue that helps recover the key needed to decode the encrypted content.

## Step 1 — Inspect the Provided Files

I started by checking the supplied files. Opening `encrypted.bin` as plain text produced unreadable characters, indicating that the content needed to be decoded.

## Step 2 — Examine the Audio in Sonic Visualiser

I opened `signal.wav` in Sonic Visualiser and inspected its waveform. It contained several distinct bursts, so I switched to the spectrogram view to look for hidden information in the frequencies.

## Step 3 — Recover the XOR Key

The spectrogram revealed the following text:

```text
KEY: DEADFREQ
```

This was the key clue for decoding the encrypted file.

## Step 4 — Decode Using CyberChef

Next, I used CyberChef and its XOR operation. I entered the encrypted content, set the key to `DEADFREQ`, and selected UTF-8.

After applying the operation, the output became readable and revealed the challenge flag.

## Step 5 — Confirm the Flag

The output from CyberChef matched the flag shown in the supplied evidence.

## Final Flag

```text
recon{sp3ctr4l_wh1sp3rs_n3v3r_l13}
```

## Tools Used

- **Sonic Visualiser** — to inspect the audio spectrogram and recover the key.
- **CyberChef** — to decode the encrypted content using XOR.

## Conclusion

The solution involved examining the audio spectrogram to find the key, then using that key with XOR in CyberChef to recover the flag.
