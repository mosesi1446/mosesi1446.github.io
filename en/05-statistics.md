---
title: Coding Statistics & Analysis
nav_order: 6
parent: English
description: Coding rate, collision rate, and keystroke-efficiency analysis of the Fengshui Input Method
permalink: /en/05-statistics/
---

{% include lang_switch.html %}

# Coding Statistics & Analysis
{: .fs-8 }

By combinatorics: one-key characters have at most 26 combinations, two-key characters at most 26×26=676, three-key characters at most 26³=17,576, and four-key characters at most 26⁴=456,976 — about 470,000 combinations in total. With three tiers of candidate keys configured, the number of code combinations expands further.

|  | Tier-1 candidate | Tier-3 candidate |
|---|---|---|
| One-key | 26 | 78 |
| Two-key | 676 | 2028 |
| Three-key | 17576 | 52728 |
| Four-key | 450,000 | 1,370,000 |
| **Total** | **470,000** | **1,420,000** |

A corpus analysis website performed statistics on 20 million characters of material: the top 5,700 most frequently used single characters account for as much as 99.98%, and the top 15,000 most frequently used words account for 90.4%. With three tiers of candidate keys configured, three-key characters alone offer about 52,700 combinations — more than enough to cover common characters and words.

The Fengshui dictionary comes with nearly 155,000 built-in entries, sufficient for the daily input needs of the vast majority of people. The detailed code-count statistics are shown below.

<div class="table-wrap"><table class="fs-table stats">
<thead><tr><th>Keys</th><th>Candidate tier</th><th>Single char</th><th>2-char</th><th>3-char</th><th>≥4-char</th><th>Subtotal</th><th>Keystrokes</th></tr></thead>
<tbody>
<tr><td rowspan="2">One-key</td><td>Tier 1</td><td>26</td><td>/</td><td>/</td><td>/</td><td rowspan="2">78</td><td rowspan="2">2</td></tr>
<tr><td>Tiers 2–3</td><td>52</td><td>/</td><td>/</td><td>/</td></tr>
<tr><td rowspan="2">Two-key</td><td>Tier 1</td><td>662</td><td>1</td><td>10</td><td>3</td><td rowspan="2">2028</td><td rowspan="2">3</td></tr>
<tr><td>Tiers 2–3</td><td>1236</td><td>27</td><td>56</td><td>33</td></tr>
<tr><td rowspan="2">Three-key</td><td>Tier 1</td><td>3928</td><td>7315</td><td>3139</td><td>2585</td><td rowspan="2">47563</td><td rowspan="2">4</td></tr>
<tr><td>Tiers 2–3</td><td>2062</td><td>14060</td><td>7050</td><td>7424</td></tr>
<tr><td rowspan="3">Four-key</td><td>Direct commit</td><td>4873</td><td>47099</td><td>23332</td><td>36328</td><td>111632</td><td>4</td></tr>
<tr><td>Tiers 2–3</td><td>608</td><td>17138</td><td>11946</td><td>13446</td><td>43138</td><td>5</td></tr>
<tr><td>Tiers 4–5</td><td>29</td><td>2159</td><td>1869</td><td>1641</td><td>5698</td><td>5</td></tr>
<tr><td colspan="2">Total</td><td>13476</td><td>87799</td><td>47402</td><td>61460</td><td colspan="2">210137</td></tr>
</tbody>
</table></div>

Converting the table above into a code-rate table, the percentages are the utilization of each tier's coding space (actual codes ÷ possible codes for that tier).

<div class="table-wrap"><table class="fs-table stats">
<thead><tr><th>Keys</th><th>Candidate tier</th><th>Single char</th><th>2-char</th><th>3-char</th><th>≥4-char</th><th>Total</th></tr></thead>
<tbody>
<tr><td rowspan="2">One-key</td><td>Tier 1</td><td>100.00%</td><td>/</td><td>/</td><td>/</td><td>100.00%</td></tr>
<tr><td>Tiers 2–3</td><td>100.00%</td><td>/</td><td>/</td><td>/</td><td>100.00%</td></tr>
<tr><td rowspan="2">Two-key</td><td>Tier 1</td><td>97.93%</td><td>0.15%</td><td>1.48%</td><td>0.44%</td><td>100.00%</td></tr>
<tr><td>Tiers 2–3</td><td>91.42%</td><td>2.00%</td><td>4.14%</td><td>2.44%</td><td>100.00%</td></tr>
<tr><td rowspan="2">Three-key</td><td>Tier 1</td><td>22.35%</td><td>41.62%</td><td>17.86%</td><td>14.71%</td><td>96.54%</td></tr>
<tr><td>Tiers 2–3</td><td>5.87%</td><td>40.00%</td><td>20.06%</td><td>21.12%</td><td>87.04%</td></tr>
<tr><td rowspan="2">Four-key</td><td>Tier 1</td><td>1.07%</td><td>10.31%</td><td>5.11%</td><td>7.95%</td><td>24.43%</td></tr>
<tr><td>Tiers 2–3</td><td>0.07%</td><td>1.88%</td><td>1.31%</td><td>1.47%</td><td>4.72%</td></tr>
</tbody>
</table></div>

From the table we can see: the one-key space is 100% utilized; the two-key tier-1 and tiers 2–3 both reach 100% (every code is equipped with all three candidate tiers); the three-key tier-1 utilization is 96.54% and tiers 2–3 is 87.04%, indicating the short-code space is fully used. The four-key space utilization is relatively low (tier-1 24.43%, tiers 2–3 4.72%), which means the four-key coding space (26⁴=456,976) is far larger than actually needed and collisions are very rare. In the three-key rows, words occupy a large share (2-char 41.62%, 3-char 17.86%, ≥4-char 14.71%), showing that common multi-character words are also assigned three-key simplified codes. Usually two to four keystrokes are enough to input the vast majority of characters and words — the input efficiency is very high.

The collision-rate analysis by key length is shown below. All 26 one-key codes are in use; the 676 two-key codes all have collisions because all three candidate tiers are configured, with a maximum collision of only 3; the three-key zero-collision rate is 6.27% with a maximum collision of 3; the four-key zero-collision rate is as high as 71.0% with a maximum collision of only 5. Overall, 162,000 characters and words use only about 129,000 codes, with no paging needed at any point — the collision control is excellent.

<div class="table-wrap"><table class="fs-table stats">
<thead><tr><th>Key length</th><th>Unique codes</th><th>Zero-collision codes</th><th>Zero-collision rate</th><th>Collision groups</th><th>Max collision</th><th>Total entries</th></tr></thead>
<tbody>
<tr><td>1-key</td><td>26</td><td>0</td><td>0.00%</td><td>26</td><td>3</td><td>78</td></tr>
<tr><td>2-key</td><td>676</td><td>0</td><td>0.00%</td><td>676</td><td>3</td><td>2028</td></tr>
<tr><td>3-key</td><td>16967</td><td>1064</td><td>6.27%</td><td>15903</td><td>3</td><td>47563</td></tr>
<tr><td>4-key</td><td>111632</td><td>79264</td><td>71.00%</td><td>32368</td><td>5</td><td>160468</td></tr>
</tbody>
</table></div>

The frequency-weighted average keystroke analysis is shown below. The overall average is only 4.05 keystrokes, and only 2.82 for single characters, showing that high-frequency characters are mostly assigned short codes — the input efficiency is extremely high. The average keystrokes for each word category all fall between 4.0 and 4.1, reflecting the evenness of code allocation.

| Category | Single char | 2-char | 3-char | ≥4-char | Overall |
|---|---|---|---|---|---|
| Avg keystrokes | 2.82 | 4.04 | 4.11 | 4.09 | 4.05 |

Statistics on the code table of all single characters are shown below. The code counts are fairly evenly distributed across all keys and tiers. In the Total column, the keys in the "米人" home area — "EDC—SDFG—HJKL—I" — carry the highest counts, exactly as designed.

<div class="table-wrap"><table class="fs-table stats">
<thead><tr><th>Key</th><th>1-key</th><th>2-key</th><th>3-key</th><th>4-key</th><th>Phonetic suppl.</th><th>Total</th></tr></thead>
<tbody>
<tr><td>A</td><td>156</td><td>86</td><td>86</td><td>32</td><td>32</td><td>392</td></tr>
<tr><td>B</td><td>116</td><td>151</td><td>159</td><td>93</td><td>178</td><td>697</td></tr>
<tr><td><strong>C</strong></td><td>155</td><td>369</td><td>308</td><td>84</td><td>220</td><td><strong>1136</strong></td></tr>
<tr><td><strong>D</strong></td><td>215</td><td>370</td><td>386</td><td>172</td><td>164</td><td><strong>1307</strong></td></tr>
<tr><td><strong>E</strong></td><td>377</td><td>295</td><td>274</td><td>156</td><td>34</td><td><strong>1136</strong></td></tr>
<tr><td><strong>F</strong></td><td>325</td><td>491</td><td>359</td><td>93</td><td>147</td><td><strong>1415</strong></td></tr>
<tr><td><strong>G</strong></td><td>255</td><td>375</td><td>252</td><td>253</td><td>182</td><td><strong>1317</strong></td></tr>
<tr><td><strong>H</strong></td><td>491</td><td>276</td><td>117</td><td>32</td><td>170</td><td><strong>1086</strong></td></tr>
<tr><td><strong>I</strong></td><td>333</td><td>366</td><td>286</td><td>170</td><td>0</td><td><strong>1155</strong></td></tr>
<tr><td><strong>J</strong></td><td>359</td><td>300</td><td>226</td><td>117</td><td>327</td><td><strong>1329</strong></td></tr>
<tr><td><strong>K</strong></td><td>365</td><td>335</td><td>474</td><td>218</td><td>123</td><td><strong>1515</strong></td></tr>
<tr><td><strong>L</strong></td><td>269</td><td>348</td><td>339</td><td>183</td><td>264</td><td><strong>1403</strong></td></tr>
<tr><td>M</td><td>309</td><td>173</td><td>196</td><td>137</td><td>166</td><td>981</td></tr>
<tr><td>N</td><td>235</td><td>231</td><td>196</td><td>94</td><td>92</td><td>848</td></tr>
<tr><td>O</td><td>204</td><td>222</td><td>124</td><td>84</td><td>7</td><td>641</td></tr>
<tr><td>P</td><td>169</td><td>216</td><td>199</td><td>221</td><td>128</td><td>933</td></tr>
<tr><td>Q</td><td>252</td><td>135</td><td>153</td><td>130</td><td>193</td><td>863</td></tr>
<tr><td>R</td><td>323</td><td>313</td><td>172</td><td>53</td><td>61</td><td>922</td></tr>
<tr><td><strong>S</strong></td><td>243</td><td>273</td><td>306</td><td>70</td><td>256</td><td><strong>1148</strong></td></tr>
<tr><td>T</td><td>288</td><td>227</td><td>38</td><td>3</td><td>151</td><td>707</td></tr>
<tr><td>U</td><td>215</td><td>265</td><td>82</td><td>13</td><td>0</td><td>575</td></tr>
<tr><td>V</td><td>411</td><td>142</td><td>179</td><td>167</td><td>0</td><td>899</td></tr>
<tr><td>W</td><td>253</td><td>269</td><td>172</td><td>101</td><td>128</td><td>923</td></tr>
<tr><td>X</td><td>177</td><td>127</td><td>151</td><td>48</td><td>240</td><td>743</td></tr>
<tr><td>Y</td><td>149</td><td>209</td><td>98</td><td>15</td><td>343</td><td>814</td></tr>
<tr><td>Z</td><td>131</td><td>64</td><td>105</td><td>89</td><td>340</td><td>729</td></tr>
</tbody>
</table></div>

## Overall Assessment

Based on the above analysis, the Fengshui Form-Phonetic Input Method has the following notable advantages:

- **Large dictionary** — 6,775 single characters and over 155,000 words, totaling 162,000 entries, covering the vast majority of characters and words needed for daily input.
- **High short-code utilization** — one-key 100%, two-key tier-3 candidates fully configured at 100%, three-key tier-1 at 96.5% and tiers 2–3 at 87.0%; the short-code space is fully utilized.
- **Excellent collision control** — the four-key zero-collision rate reaches 71.0%, with a maximum collision count of only 5; no paging is needed throughout.
- **High keystroke efficiency** — the frequency-weighted average is only 4.05 keystrokes, and only 2.82 for single characters; high-frequency characters are all assigned short codes.
- **Even key distribution** — the 26 letter keys are fairly evenly distributed across code positions, with the home key area (EDC—SDFG—HJKL—I) used most frequently, in line with ergonomic design.
