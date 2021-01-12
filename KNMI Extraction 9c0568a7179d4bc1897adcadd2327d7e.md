# KNMI Extraction

[W12_KNMI_complete.pdf](KNMI%20Extraction%209c0568a7179d4bc1897adcadd2327d7e/W12_KNMI_complete.pdf)

The data KNMI provides has this shape:

![KNMI%20Extraction%209c0568a7179d4bc1897adcadd2327d7e/Untitled.png](KNMI%20Extraction%209c0568a7179d4bc1897adcadd2327d7e/Untitled.png)

To synchronise this with the production data a date-time column would be ideal. Since all information is available to do that this was the chosen approach.

After adding the datetime and renaming the columns to their respective names the DataFrame looks a little like this:

![KNMI%20Extraction%209c0568a7179d4bc1897adcadd2327d7e/Untitled%201.png](KNMI%20Extraction%209c0568a7179d4bc1897adcadd2327d7e/Untitled%201.png)

This DataFrame is then saved as a pickle and very convenient to add to the other notebooks where any weather data is required.