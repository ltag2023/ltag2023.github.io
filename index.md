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
        <td>en:is love I can be sure of<br>zh:是否能给我安全感 shì fǒ néng gěi wǒ ān quán gǎn</td>
        <td>这就是爱，我可以肯定的爱吗 zhè jiù shì ài，wǒ kě yǐ kěn dìng de ài ma</td>
        <td>是爱我能确定 shì ài wǒ néng kěn dìng</td>
        <td>是爱我可以肯定 shì ài wǒ kě yǐ kěn dìng</td>
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
        <td>en:I need you here I need you here to wipe away my tears<br>zh:我需要你 我需要你帮我抹去泪水 wǒ xū yào nǐ wǒ xū yào nǐ bāng wǒ mǒ qù lèi shuǐ</td>
        <td>我需要你 我需要你在这里来擦去眼泪 wǒ xū yào nǐ wǒ xū yào nǐ zài zhè lǐ cā qù yǎn lèi</td>
        <td>我需要你 我需要你擦干眼泪 wǒ xū yào nǐ wǒ xū yào nǐ cā gān yǎn lèi</td>
        <td>我需要你 我需要你擦干眼泪 wǒ xū yào nǐ wǒ xū yào nǐ cā gān lèi shǔi</td>
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
        <td>en:Aint nothing but a heartache Tell Me Why Aint nothing but a mistake<br>zh:为什么让我心痛 告诉我 为什么你不行动 wèi shén mè ràng wǒ xīn tòng gào sù wǒ wèi shén mè nǐ bù xíng dòng</td>
        <td>不过是心痛而已 告诉我 只不过是个错误 bú guò shì xīn tòng ér yǐ gào sù wǒ zhǐ bú guò shì gè cuò wu</td>
        <td>不过是心痛 告诉我 不过是个错 bú guò shì xīn tòng gào sù wǒ bú guò shì gè cuò</td>
        <td>没什么只是心痛 告诉我 没什么只是个错 méi shén mè zhǐ shì xīn tòng gào sù wǒ méi shén mè zhǐ shì gè cuò</td>
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

5. "So full of the superficial Some people want it all But I don't want nothing at all" from *"If I Ain't Got You"*

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
        <td>en:So full of the superficial Some people want it all But I don't want nothing at all<br>zh:生活实在肤浅至极 有人想拥有一切 而我什么都不缺</td>
        <td>如此充满了肤浅的 有些人想要一切 但我什么也不想要</td>
        <td>如此的肤浅 有人都想要 却一无所有</td>
        <td>如此的肤浅 有些人都想要 却什么都不要</td>
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

6. "When the rain is blowing in your face And the whole world is on your case" from *"Make you feel my love"*

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
        <td>en:When the rain is blowing in your face And the whole world is on your case<br>zh:当雨吹打在你的脸上 全世界压在你行李箱</td>
        <td>当雨水在的脸上吹来时 整个世界都在你的案子上</td>
        <td>当雨打在你脸上 全世界都在你左右</td>
        <td>当雨打在你的脸上 整个世界都在你的左右</td>
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

1. "也许当时忙着微笑和哭泣 忙着追逐天空中的流星" from *"小幸运"*

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
        <td>zh:也许当时忙着微笑和哭泣 忙着追逐天空中的流星<br>en:Perhaps I've been busy smiling and shedding tears Or can't help chasing in the sky pretty meteors</td>
        <td>Perhaps I was busy smiling and crying at the time of the meeting I am busy chasing after the shooting stars that are in the sky</td>
        <td>Maybe I was busy smiling and crying busy chasing the shooting in the sky</td>
        <td>Maybe I was busy with a smile and a cry busy chasing the stars in the sky</td>
    </tr>
    <tr style="height: 400%;">
        <th scope="row">scores</th>
        <td><img align="center" src="resources/scores/zh_en/gt/1.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/zh_en/gagast/1.svg" style="display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/zh_en/baseline/1.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/zh_en/ltag/1.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
    </tr>
    </tbody>
</table>

2. "你张开了双翼 遇见你的注定" from *"小幸运"*

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
        <td>zh:你张开了双翼 遇见你的注定<br>en:You turn over old memory Come across your destiny</td>
        <td>You open up your wings for me It ’s the fate to meet you when I meet you</td>
        <td>you spread your wings to meet you is meant to</td>
        <td>You have spread your wings To meet you is destined</td>
    </tr>
    <tr style="height: 400%;">
        <th scope="row">scores</th>
        <td><img align="center" src="resources/scores/zh_en/gt/2.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/zh_en/gagast/2.svg" style="display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/zh_en/baseline/2.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/zh_en/ltag/2.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
    </tr>
    </tbody>
</table>

3. "好不好有亏欠我们都别再追究" from *"说散就散"*

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
        <td>zh:好不好有亏欠我们都别再追究<br>en:Good or bad no matter what we just let go</td>
        <td>Is it good to have a debt to pay ? We don't have to pursue it.</td>
        <td>What good is there a debt we don't have to follow</td>
        <td>We owe each other good or bad don't hold it up</td>
    </tr>
    <tr style="height: 400%;">
        <th scope="row">scores</th>
        <td><img align="center" src="resources/scores/zh_en/gt/3.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/zh_en/gagast/3.svg" style="display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/zh_en/baseline/3.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
        <td><img align="center" src="resources/scores/zh_en/ltag/3.svg" style="  display: block; margin-left: auto; margin-right: auto; width: 800%; height: 800%;" /></td>
    </tr>
    </tbody>
</table>