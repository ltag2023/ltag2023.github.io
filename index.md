<script type="text/javascript" async src="//cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>
# Translate the Beauty in Songs:Jointly Learning to Align Melody and Translate Lyrics

Under Review
ACL 2023 ARR October Submission

## Abstract

Song translation requires both translation of lyrics and alignment of music notes so that the resulting verse can be sung to the accompanying melody, which is a challenging problem that has attracted some interests in different aspects of the translation process. In this paper, we propose <u>L</u>yrics-Melody <u>T</u>ranslation with <u>A</u>daptive <u>G</u>rouping (LTAG), a holistic solution to automatic song translation by jointly modeling lyrics translation and lyrics-melody alignment. It is a novel encoder-decoder framework that can simultaneously translate the source lyrics and determine the number of aligned notes at each decoding step through an adaptive note grouping module. To address data scarcity, we commissioned a small amount of training data annotated specifically for this task and used large amounts of augmented data through back-translation. Experiments conducted on an English-Chinese song translation data set show the effectiveness of our model in both automatic and human evaluations.

## Translated Scores and Sythesized Singing Audio Samples

<img align="center" src="resources/model.png" style="  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 100%;" />
<img align="center" src="resources/enc_dec_act.png" style="  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 100%;" />

### En $\rightarrow$ Zh

0. from ``小幸运''
    <table style='width: 100%;'>
        <thead>
        <tr>
            <th></th>
            <th>Source and Reference</th>
            <th>GagaST</th>
            <th>LTAG-cls</th>
            <th>LTAG</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">lyrics text</th>
            <td>en:xxxxx<br>
                zh:xxxxx</td>
            <td>xxxx</td>
            <td>xxxx</td>
            <td>xxxx</td>
        </tr>
        <tr>
            <th scope="row">scores</th>
            <td><img align="center" src="resources/scores/en_zh/gt/0.png" style="  display: block; margin-left: auto;
margin-right: auto; width: 100%;" /></td>
            <td><img align="center" src="resources/scores/en_zh/gagast/0.png" style="  display: block; margin-left: auto;
margin-right: auto; width: 100%;" /></td>
            <td><img align="center" src="resources/scores/en_zh/baseline/0.png" style="  display: block; margin-left: auto;
margin-right: auto; width: 100%;" /></td>
            <td><img align="center" src="resources/scores/en_zh/ltag/0.png" style="  display: block; margin-left: auto;
margin-right: auto; width: 100%;" /></td>
        </tr>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/en_zh/gt/0.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/en_zh/gagast/0.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/en_zh/baseline/0.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/en_zh/ltag/0.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>
