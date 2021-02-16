# Citizen Browser - Facebook flags
This repository contains the findings featured in our story: "[Trump's False Posts Were Treated with Kid Gloves by Facebook](https://themarkup.org/citizen-browser/2021/02/16/trumps-false-posts-were-treated-with-kid-gloves-by-facebook)" from our series [Citizen Browser](https://themarkup.org/series/citizen-browser/).

Our methodology for the overall Citizen Browser project is described in "[How We Built a Facebook Inspector](https://themarkup.org/citizen-browser/2021/01/05/how-we-built-a-facebook-inspector)."

## Query parameters

### Time Frame
We sought to examine where, how, and why Facebook was applying its informational flags to posts. We examined all posts sent to our panelists between **Dec. 1, 2020**, and **Jan. 31, 2021**.

### Flags
We filtered our snapshot to only show posts in which we captured a flag message.

### Exclusions
We excluded any posts flagged as sponsored, any posts that were clearly advertisements, and any links that were not associated with the activity surrounding the riot. We removed the `poster` and `poster_url` fields for accounts that were not marked as verfied by Facebook.

We excluded any posts made by Facebook itself.

## Data files

`data/biden_flagged_posts.csv`
This CSV file contains the posts made by Joe Biden that received an informational flag by Facebook, shown to our Citizen Browser panelists from our snapshot. 

`data/trump_flagged_posts.csv`
This CSV file contains the posts made by Donald Trump that received an informational flag by Facebook, shown to our Citizen Browser panelists from our snapshot. 

`data/all_flagged_posts.csv`
This CSV file contains all of the posts in our snapshot that had informational flag messages.

`data/flag_counts.csv`
This CSV file contains all of the unique informational flag messages we found in our snapshot.

### Data dictionary:
This applies to `data/biden_flagged_posts.csv` and `data/trump_flagged_posts`.
<table border="0" class="dataframe">
  <thead>
    <tr style="text-align: left;">
      <th>Column</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>timestamp_EST</strong></td>
      <td>The date the post was observed in Eastern Standard Time. Format: `YYYY-MM-DD HH:MM:SS`</td>
    </tr>
    <tr>
      <td><strong>poster_url</strong></td>
      <td>The URL of the Facebook account that made the post.</td>
    </tr>
    <tr>
      <td><strong>post_text</strong></td>
      <td>The text of the post.</td>
    </tr>
    <tr>
      <td><strong>image_alts</strong></td>
      <td>The text extracted from the image shared on the post. This is often incomplete. </td>
    </tr>
    <tr>
      <td><strong>flags</strong></td>
      <td>The text of the Facebook flag attached to the post.</td>
    </tr>
  </tbody>
</table>

---

This applies to `data/all_flagged_posts.csv`.

Each row represents one post that appeared on a panelist's timeline. These are the posts in our snapshot that had a flag message attached to them. We removed the `poster` and `poster_url` fields for accounts that were not marked as verfied by Facebook.

<table border="0" class="dataframe">
  <thead>
    <tr style="text-align: left;">
      <th>Column</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>timestamp_EST</strong></td>
      <td>The date the post was observed in Eastern Standard Time. Format: `YYYY-MM-DD HH:MM:SS`</td>
    </tr>
    <tr>
      <td><strong>user_id</strong></td>
      <td>A unique identifier of the panelist who was shown this post.</td>
    </tr>
    <tr>
      <td><strong>post_text</strong></td>
      <td>The text of the post.</td>
    </tr>
    <tr>
      <td><strong>poster_url</strong></td>
      <td>The URL of the Facebook account that made the post.</td>
    </tr>
    <tr>
      <td><strong>poster</strong></td>
      <td>The name of the Facebook account that made the post.</td>
    </tr>
    <tr>
      <td><strong>is_verified</strong></td>
      <td>Was the account that made the post a Facebook "verified" account?</td>
    </tr> 
     <tr>
      <td><strong>flags</strong></td>
      <td>The text of the Facebook flag attached to the post.</td>
    </tr>
    <tr>
      <td><strong>image_alts</strong></td>
      <td>The text extracted from the image shared on the post. This is often incomplete. </td>
    </tr>
    <tr>
      <td><strong>vote_2020</strong></td>
      <td>How the panelist who was shown the post voted in the 2020 U.S. presidential election.</td>
    </tr>
  </tbody>
</table>

---

This applies to `data/flag_counts.csv`.
<table border="0" class="dataframe">
  <thead>
    <tr style="text-align: left;">
      <th>Column</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>flag_message</strong></td>
      <td>The text of the Facebook flag attached to the post.</td>
    </tr>
    <tr>
      <td><strong>count</strong></td>
      <td>The number of times the flag was observed in our snapshot.</td>
    </tr>
  </tbody>
</table>


## Licensing
Copyright 2021, The Markup News Inc.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.