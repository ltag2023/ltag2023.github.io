# Translate the Beauty in Songs: Jointly Learning to Align Melody and Translate Lyrics

Under Review
ACL 2023 ARR October Submission

## Abstract

Song translation requires both translation of lyrics and alignment of music notes so that the resulting verse can be sung to the accompanying melody, which is a challenging problem that has attracted some interests in different aspects of the translation process. In this paper, we propose <u>L</u>yrics-Melody <u>T</u>ranslation with <u>A</u>daptive <u>G</u>rouping (LTAG), a holistic solution to automatic song translation by jointly modeling lyrics translation and lyrics-melody alignment. It is a novel encoder-decoder framework that can simultaneously translate the source lyrics and determine the number of aligned notes at each decoding step through an adaptive note grouping module. To address data scarcity, we commissioned a small amount of training data annotated specifically for this task and used large amounts of augmented data through back-translation. Experiments conducted on an English-Chinese song translation data set show the effectiveness of our model in both automatic and human evaluations.
<img align="center" src="resources/model.svg" style="  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 100%;" />
<img align="center" src="resources/enc_dec_act.svg" style="  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 100%;" />

## Translated Scores and Sythesized Singing Audio Samples
### En -> Zh

0. "Is love I can be sure of" from *"Will You Still Love Me Tomorrow"*

<table style='width: 200%;'>
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
    <tr style="height: 50%;">
        <th scope="row">lyrics text</th>
        <td>en:is love I can be sure of<br>zh:是否能给我安全感</td>
        <td>这就是爱，我可以肯定的爱吗</td>
        <td>是爱我能确定</td>
        <td>是爱我可以肯定</td>
    </tr>
    <tr style="height: 400%;">
        <th scope="row">scores</th>
        <td><img align="center" src="resources/scores/en_zh/gt/0.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/gagast/0.svg" style="display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/baseline/0.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/ltag/0.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
    </tr>
    <tr style="height: 50%;">
        <th scope="row">wav</th>
        <td><audio controls="" ><source src="resources/audio/en_zh/gt/0.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/gagast/0.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/baseline/0.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/ltag/0.wav" type="audio/wav"></audio></td>
    </tr>
    </tbody>
</table>

1. "I need you here I need you here to wipe away my tears" from *"Run To You"*

<table style='width: 200%;'>
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
    <tr style="height: 50%;">
        <th scope="row">lyrics text</th>
        <td>en:I need you here I need you here to wipe away my tears<br>zh:我需要你 我需要你帮我抹去泪水</td>
        <td>我需要你 我需要你在这里来擦去眼泪</td>
        <td>我需要你 我需要你擦干眼泪</td>
        <td>我需要你 我需要你擦干泪水</td>
    </tr>
    <tr style="height: 400%;">
        <th scope="row">scores</th>
        <td><img align="center" src="resources/scores/en_zh/gt/1.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/gagast/1.svg" style="display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/baseline/1.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/ltag/1.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
    </tr>
    <tr style="height: 50%;">
        <th scope="row">wav</th>
        <td><audio controls="" ><source src="resources/audio/en_zh/gt/1.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/gagast/1.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/baseline/1.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/ltag/1.wav" type="audio/wav"></audio></td>
    </tr>
    </tbody>
</table>

2. "Aint nothing but a heartache Tell Me Why Aint nothing but a mistake" from *"I Want It That Way"*

<table style='width: 200%;'>
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
    <tr style="height: 50%;">
        <th scope="row">lyrics text</th>
        <td>en:Aint nothing but a heartache Tell Me Why Aint nothing but a mistake<br>zh:为什么让我心痛 告诉我 为什么你不行动</td>
        <td>不过是心痛而已 告诉我 不过是个错而已</td>
        <td>不过是心痛 告诉我 不过是个错</td>
        <td>没什么只是心痛 告诉我 没什么只是个错</td>
    </tr>
    <tr style="height: 400%;">
        <th scope="row">scores</th>
        <td><img align="center" src="resources/scores/en_zh/gt/2.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/gagast/2.svg" style="display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/baseline/2.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/ltag/2.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
    </tr>
    <tr style="height: 50%;">
        <th scope="row">wav</th>
        <td><audio controls="" ><source src="resources/audio/en_zh/gt/2.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/gagast/2.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/baseline/2.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/ltag/2.wav" type="audio/wav"></audio></td>
    </tr>
    </tbody>
</table>

3. "And I'm thinking about how people fall in love in mysterious ways Maybe just the touch of a hand" from *"Thinking Out Load"*

<table style='width: 200%;'>
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
    <tr style="height: 50%;">
        <th scope="row">lyrics text</th>
        <td>en:And I'm thinking about how people fall in love in mysterious ways Maybe just the touch of a hand<br>zh:我一直在想人们如何神秘地坠入爱河 或许只是轻碰了手</td>
        <td>而且我在想着人们是如何以神秘的方式坠入爱河 也许仅仅是一只手</td>
        <td>我在想人们是如何神秘地坠落 也许只是一触即发</td>
        <td>我在想人们如何神秘地坠入爱河 也许只是一触即发</td>
    </tr>
    <tr style="height: 400%;">
        <th scope="row">scores</th>
        <td><img align="center" src="resources/scores/en_zh/gt/3.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/gagast/3.svg" style="display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/baseline/3.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/ltag/3.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
    </tr>
    <tr style="height: 50%;">
        <th scope="row">wav</th>
        <td><audio controls="" ><source src="resources/audio/en_zh/gt/3.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/gagast/3.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/baseline/3.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/ltag/3.wav" type="audio/wav"></audio></td>
    </tr>
    </tbody>
</table>

4. "Kiss me under the light of a thousand stars" from *"Thinking Out Load"*

<table style='width: 200%;'>
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
    <tr style="height: 50%;">
        <th scope="row">lyrics text</th>
        <td>en:Kiss me under the light of a thousand stars<br>zh:在星空下吻我吧</td>
        <td>在成千上万颗星星的光下吻我</td>
        <td>千星之光下吻我</td>
        <td>在千星之光下吻我</td>
    </tr>
    <tr style="height: 400%;">
        <th scope="row">scores</th>
        <td><img align="center" src="resources/scores/en_zh/gt/4.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/gagast/4.svg" style="display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/baseline/4.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/ltag/4.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
    </tr>
    <tr style="height: 50%;">
        <th scope="row">wav</th>
        <td><audio controls="" ><source src="resources/audio/en_zh/gt/4.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/gagast/4.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/baseline/4.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/ltag/4.wav" type="audio/wav"></audio></td>
    </tr>
    </tbody>
</table>

5. "Is love I can be sure of" from *"Will You Still Love Me Tomorrow"*

<table style='width: 200%;'>
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
    <tr style="height: 50%;">
        <th scope="row">lyrics text</th>
        <td>en:is love I can be sure of<br>zh:是否能给我安全感</td>
        <td>这就是爱，我可以肯定的爱吗</td>
        <td>是爱我能确定</td>
        <td>是爱我可以肯定</td>
    </tr>
    <tr style="height: 400%;">
        <th scope="row">scores</th>
        <td><img align="center" src="resources/scores/en_zh/gt/5.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/gagast/5.svg" style="display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/baseline/5.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/ltag/5.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
    </tr>
    <tr style="height: 50%;">
        <th scope="row">wav</th>
        <td><audio controls="" ><source src="resources/audio/en_zh/gt/5.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/gagast/5.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/baseline/5.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/ltag/5.wav" type="audio/wav"></audio></td>
    </tr>
    </tbody>
</table>

6. "Is love I can be sure of" from *"Will You Still Love Me Tomorrow"*

<table style='width: 200%;'>
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
    <tr style="height: 50%;">
        <th scope="row">lyrics text</th>
        <td>en:is love I can be sure of<br>zh:是否能给我安全感</td>
        <td>这就是爱，我可以肯定的爱吗</td>
        <td>是爱我能确定</td>
        <td>是爱我可以肯定</td>
    </tr>
    <tr style="height: 400%;">
        <th scope="row">scores</th>
        <td><img align="center" src="resources/scores/en_zh/gt/6.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/gagast/6.svg" style="display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/baseline/6.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/en_zh/ltag/6.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
    </tr>
    <tr style="height: 50%;">
        <th scope="row">wav</th>
        <td><audio controls="" ><source src="resources/audio/en_zh/gt/6.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/gagast/6.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/baseline/6.wav" type="audio/wav"></audio></td>
        <td><audio controls="" ><source src="resources/audio/en_zh/ltag/6.wav" type="audio/wav"></audio></td>
    </tr>
    </tbody>
</table>

### Zh -> En

0. "她会有多幸运" from *"小幸运"*

<table style='width: 200%;'>
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
    <tr style="height: 50%;">
        <th scope="row">lyrics text</th>
        <td>zh:她会有多幸运<br>en:How lucky she will be</td>
        <td>How lucky she would be to be</td>
        <td>How lucky would she be</td>
        <td>How lucky would she be</td>
    </tr>
    <tr style="height: 400%;">
        <th scope="row">scores</th>
        <td><img align="center" src="resources/scores/zh_en/gt/0.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/zh_en/gagast/0.svg" style="display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/zh_en/baseline/0.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/zh_en/ltag/0.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
    </tr>
    </tbody>
</table>