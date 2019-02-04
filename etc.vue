<template>
  <div class="hello animated fadeIn">
<h1>利用する鉄道を選択してください</h1>
<p>※数が多すぎるので検索機能を使って下さい。(CTRFキー+Fキー)<br>レイアウト考え中です。</p>
<input type="checkbox" v-model="checkedNames" value="土佐くろしお鉄道線">土佐くろしお鉄道線
<input type="checkbox" v-model="checkedNames" value="愛知環状鉄道">愛知環状鉄道
<input type="checkbox" v-model="checkedNames" value="三陸鉄道線">三陸鉄道線
<input type="checkbox" v-model="checkedNames" value="智頭急行線">智頭急行線
<input type="checkbox" v-model="checkedNames" value="あおなみ線">あおなみ線
<input type="checkbox" v-model="checkedNames" value="神戸市営地下鉄">神戸市営地下鉄
<input type="checkbox" v-model="checkedNames" value="福北ゆたか線">福北ゆたか線
<input type="checkbox" v-model="checkedNames" value="筑豊本線">筑豊本線
<input type="checkbox" v-model="checkedNames" value="若松線">若松線
<input type="checkbox" v-model="checkedNames" value="東山線">東山線
<input type="checkbox" v-model="checkedNames" value="神戸線">神戸線
<input type="checkbox" v-model="checkedNames" value="宝塚線">宝塚線
<input type="checkbox" v-model="checkedNames" value="鶴舞線">鶴舞線
<input type="checkbox" v-model="checkedNames" value="名港線">名港線
<input type="checkbox" v-model="checkedNames" value="小田原線">小田原線
<input type="checkbox" v-model="checkedNames" value="江ノ島線">江ノ島線
<input type="checkbox" v-model="checkedNames" value="東葉高速線">東葉高速線
<input type="checkbox" v-model="checkedNames" value="東武アーバンパークライン">東武アーバンパークライン
<input type="checkbox" v-model="checkedNames" value="JR京都線">JR京都線
<input type="checkbox" v-model="checkedNames" value="JR神戸線">JR神戸線
<input type="checkbox" v-model="checkedNames" value="JR宝塚線">JR宝塚線
<input type="checkbox" v-model="checkedNames" value="拝島線">拝島線
<input type="checkbox" v-model="checkedNames" value="国分寺線">国分寺線
<input type="checkbox" v-model="checkedNames" value="東武スカイツリーライン･伊勢崎線">東武スカイツリーライン･伊勢崎線
<input type="checkbox" v-model="checkedNames" value="空港線･箱崎線">空港線･箱崎線
<input type="checkbox" v-model="checkedNames" value="筑肥線･地下鉄（直通列車）">筑肥線･地下鉄（直通列車）
<input type="checkbox" v-model="checkedNames" value="東海道本線（名古屋地区）">東海道本線（名古屋地区）
<input type="checkbox" v-model="checkedNames" value="いわて銀河鉄道線">いわて銀河鉄道線
<input type="checkbox" v-model="checkedNames" value="JR東西線">JR東西線
<input type="checkbox" v-model="checkedNames" value="特急電車">特急電車
<input type="checkbox" v-model="checkedNames" value="愛知環状鉄道線">愛知環状鉄道線
<input type="checkbox" v-model="checkedNames" value="橿原線">橿原線
<input type="checkbox" v-model="checkedNames" value="京都線">京都線
<input type="checkbox" v-model="checkedNames" value="名古屋線">名古屋線
<input type="checkbox" v-model="checkedNames" value="志摩線">志摩線
<input type="checkbox" v-model="checkedNames" value="鳥羽線">鳥羽線
<input type="checkbox" v-model="checkedNames" value="常滑線">常滑線
<input type="checkbox" v-model="checkedNames" value="空港線">空港線
<input type="checkbox" v-model="checkedNames" value="南リアス線">南リアス線
<input type="checkbox" v-model="checkedNames" value="南海本線">南海本線
<input type="checkbox" v-model="checkedNames" value="東海道本線（静岡地区）">東海道本線（静岡地区）
<input type="checkbox" v-model="checkedNames" value="押上線">押上線
<input type="checkbox" v-model="checkedNames" value="北総線">北総線
<input type="checkbox" v-model="checkedNames" value="九州新幹線">九州新幹線
<input type="checkbox" v-model="checkedNames" value="大阪線">大阪線
<input type="checkbox" v-model="checkedNames" value="南大阪線">南大阪線
<input type="checkbox" v-model="checkedNames" value="目黒線">目黒線
<input type="checkbox" v-model="checkedNames" value="埼玉高速鉄道線">埼玉高速鉄道線
<input type="checkbox" v-model="checkedNames" value="田園都市線">田園都市線
<input type="checkbox" v-model="checkedNames" value="京王線">京王線
<input type="checkbox" v-model="checkedNames" value="天神大牟田線">天神大牟田線
<input type="checkbox" v-model="checkedNames" value="京成本線">京成本線
<input type="checkbox" v-model="checkedNames" value="ポートライナー">ポートライナー
<input type="checkbox" v-model="checkedNames" value="六甲ライナー">六甲ライナー
<input type="checkbox" v-model="checkedNames" value="大師線">大師線
<input type="checkbox" v-model="checkedNames" value="千里線">千里線
<input type="checkbox" v-model="checkedNames" value="東急多摩川線">東急多摩川線
<input type="checkbox" v-model="checkedNames" value="常総線">常総線
<input type="checkbox" v-model="checkedNames" value="池上線">池上線
<input type="checkbox" v-model="checkedNames" value="井の頭線">井の頭線
<input type="checkbox" v-model="checkedNames" value="大糸線（北陸地区）">大糸線（北陸地区）
<input type="checkbox" v-model="checkedNames" value="大糸線（信越地区）">大糸線（信越地区）
<input type="checkbox" v-model="checkedNames" value="JRゆめ咲線">JRゆめ咲線
<input type="checkbox" v-model="checkedNames" value="JR奈良線">JR奈良線
<input type="checkbox" v-model="checkedNames" value="北陸本線（北陸地区）">北陸本線（北陸地区）
<input type="checkbox" v-model="checkedNames" value="山陰本線（中国地区）">山陰本線（中国地区）
<input type="checkbox" v-model="checkedNames" value="西武新宿線">西武新宿線
<input type="checkbox" v-model="checkedNames" value="山陽本線（中国地区）">山陽本線（中国地区）
<input type="checkbox" v-model="checkedNames" value="名古屋本線">名古屋本線
<input type="checkbox" v-model="checkedNames" value="東横線">東横線
<input type="checkbox" v-model="checkedNames" value="池袋線">池袋線
<input type="checkbox" v-model="checkedNames" value="西武有楽町線">西武有楽町線
<input type="checkbox" v-model="checkedNames" value="東京メトロ南北線">東京メトロ南北線
<input type="checkbox" v-model="checkedNames" value="小田急特急">小田急特急
<input type="checkbox" v-model="checkedNames" value="高山本線（東海地区）">高山本線（東海地区）
<input type="checkbox" v-model="checkedNames" value="羽越本線（信越地区）">羽越本線（信越地区）
<input type="checkbox" v-model="checkedNames" value="山陰本線（近畿地区）">山陰本線（近畿地区）
<input type="checkbox" v-model="checkedNames" value="みなとみらい線">みなとみらい線
<input type="checkbox" v-model="checkedNames" value="西武秩父線">西武秩父線
<input type="checkbox" v-model="checkedNames" value="只見線（東北地区）">只見線（東北地区）
<input type="checkbox" v-model="checkedNames" value="磐越西線（東北地区）">磐越西線（東北地区）
<input type="checkbox" v-model="checkedNames" value="東上本線">東上本線
<input type="checkbox" v-model="checkedNames" value="水郡線（東北地区）">水郡線（東北地区）
<input type="checkbox" v-model="checkedNames" value="JR宇都宮線">JR宇都宮線
<input type="checkbox" v-model="checkedNames" value="瀬戸線">瀬戸線
<input type="checkbox" v-model="checkedNames" value="西神">西神
<input type="checkbox" v-model="checkedNames" value="海岸線">海岸線
<input type="checkbox" v-model="checkedNames" value="山陽線（近畿地区）">山陽線（近畿地区）
<input type="checkbox" v-model="checkedNames" value="常磐線（関東地区）">常磐線（関東地区）
<input type="checkbox" v-model="checkedNames" value="西神･山手線">西神･山手線
<input type="checkbox" v-model="checkedNames" value="信越本線（信越地区）">信越本線（信越地区）
<input type="checkbox" v-model="checkedNames" value="羽越本線（東北地区）">羽越本線（東北地区）
<input type="checkbox" v-model="checkedNames" value="箕面線">箕面線
<input type="checkbox" v-model="checkedNames" value="ブルーライン">ブルーライン
<input type="checkbox" v-model="checkedNames" value="東武特急">東武特急
<input type="checkbox" v-model="checkedNames" value="東武日光線">東武日光線
<input type="checkbox" v-model="checkedNames" value="智頭線">智頭線
<input type="checkbox" v-model="checkedNames" value="北陸本線（近畿地区）">北陸本線（近畿地区）
<input type="checkbox" v-model="checkedNames" value="関西本線（東海地区）">関西本線（東海地区）
<input type="checkbox" v-model="checkedNames" value="西武園線">西武園線
<input type="checkbox" v-model="checkedNames" value="多摩湖線">多摩湖線
<input type="checkbox" v-model="checkedNames" value="特急レッドアロー">特急レッドアロー
<input type="checkbox" v-model="checkedNames" value="瀬戸大橋線（中国地区）">瀬戸大橋線（中国地区）
<input type="checkbox" v-model="checkedNames" value="瀬戸大橋線（四国地区）">瀬戸大橋線（四国地区）
<input type="checkbox" v-model="checkedNames" value="ゆとりーとライン">ゆとりーとライン
<input type="checkbox" v-model="checkedNames" value="米坂線（東北地区）">米坂線（東北地区）
<input type="checkbox" v-model="checkedNames" value="米坂線（信越地区）">米坂線（信越地区）
<input type="checkbox" v-model="checkedNames" value="高野線（汐見橋方面）">高野線（汐見橋方面）
<input type="checkbox" v-model="checkedNames" value="多摩線">多摩線
<input type="checkbox" v-model="checkedNames" value="特急ロマンスカー">特急ロマンスカー
<input type="checkbox" v-model="checkedNames" value="磐越西線（信越地区）">磐越西線（信越地区）
<input type="checkbox" v-model="checkedNames" value="信越本線（関東地区）">信越本線（関東地区）
<input type="checkbox" v-model="checkedNames" value="篠栗線（福北ゆたか線）">篠栗線（福北ゆたか線）
<input type="checkbox" v-model="checkedNames" value="各務原線">各務原線
<input type="checkbox" v-model="checkedNames" value="特急りょうもう">特急りょうもう
<input type="checkbox" v-model="checkedNames" value="遠州鉄道線">遠州鉄道線
<input type="checkbox" v-model="checkedNames" value="中央本線（関東地区）">中央本線（関東地区）
<input type="checkbox" v-model="checkedNames" value="静岡鉄道線">静岡鉄道線
<input type="checkbox" v-model="checkedNames" value="阪急宝塚線">阪急宝塚線
<input type="checkbox" v-model="checkedNames" value="高山本線（北陸地区）">高山本線（北陸地区）
<input type="checkbox" v-model="checkedNames" value="南海特急">南海特急
<input type="checkbox" v-model="checkedNames" value="高野線">高野線
<input type="checkbox" v-model="checkedNames" value="特急こうや">特急こうや
<input type="checkbox" v-model="checkedNames" value="りんかん">りんかん
<input type="checkbox" v-model="checkedNames" value="特急こうや･りんかん">特急こうや･りんかん
<input type="checkbox" v-model="checkedNames" value="只見線（信越地区）">只見線（信越地区）
<input type="checkbox" v-model="checkedNames" value="都営新宿線">都営新宿線
<input type="checkbox" v-model="checkedNames" value="名鉄空港線">名鉄空港線
<input type="checkbox" v-model="checkedNames" value="伊豆急行線">伊豆急行線
<input type="checkbox" v-model="checkedNames" value="和歌山港線">和歌山港線
<input type="checkbox" v-model="checkedNames" value="特急サザン">特急サザン
<input type="checkbox" v-model="checkedNames" value="三河線">三河線
<input type="checkbox" v-model="checkedNames" value="泉北高速鉄道線">泉北高速鉄道線
<input type="checkbox" v-model="checkedNames" value="泉北高速線">泉北高速線
<input type="checkbox" v-model="checkedNames" value="豊島線">豊島線
<input type="checkbox" v-model="checkedNames" value="越生線">越生線
<input type="checkbox" v-model="checkedNames" value="中央本線（信越地区）">中央本線（信越地区）
<input type="checkbox" v-model="checkedNames" value="肥薩おれんじ鉄道線">肥薩おれんじ鉄道線
<input type="checkbox" v-model="checkedNames" value="天竜浜名湖線">天竜浜名湖線
<input type="checkbox" v-model="checkedNames" value="南海空港線">南海空港線
<input type="checkbox" v-model="checkedNames" value="特急ラピート">特急ラピート
<input type="checkbox" v-model="checkedNames" value="吉野線">吉野線
<input type="checkbox" v-model="checkedNames" value="犬山線">犬山線
<input type="checkbox" v-model="checkedNames" value="長野電鉄線">長野電鉄線
<input type="checkbox" v-model="checkedNames" value="上飯田線">上飯田線
<input type="checkbox" v-model="checkedNames" value="名城線">名城線
<input type="checkbox" v-model="checkedNames" value="山陽線">山陽線
<input type="checkbox" v-model="checkedNames" value="特急ミュースカイ">特急ミュースカイ
<input type="checkbox" v-model="checkedNames" value="特急スペーシア">特急スペーシア
<input type="checkbox" v-model="checkedNames" value="千日前線">千日前線
<input type="checkbox" v-model="checkedNames" value="近鉄特急">近鉄特急
<input type="checkbox" v-model="checkedNames" value="阪神本線">阪神本線
<input type="checkbox" v-model="checkedNames" value="阪神なんば線">阪神なんば線
<input type="checkbox" v-model="checkedNames" value="神戸高速線">神戸高速線
<input type="checkbox" v-model="checkedNames" value="大井町線">大井町線
<input type="checkbox" v-model="checkedNames" value="千葉線">千葉線
<input type="checkbox" v-model="checkedNames" value="千原線">千原線
<input type="checkbox" v-model="checkedNames" value="鈴鹿線">鈴鹿線
<input type="checkbox" v-model="checkedNames" value="狭山線">狭山線
<input type="checkbox" v-model="checkedNames" value="成田スカイアクセス線">成田スカイアクセス線
<input type="checkbox" v-model="checkedNames" value="北リアス線">北リアス線
<input type="checkbox" v-model="checkedNames" value="井原線">井原線
<input type="checkbox" v-model="checkedNames" value="東成田線">東成田線
<input type="checkbox" v-model="checkedNames" value="富山地鉄電車">富山地鉄電車
<input type="checkbox" v-model="checkedNames" value="長野線">長野線
<input type="checkbox" v-model="checkedNames" value="急行列車">急行列車
<input type="checkbox" v-model="checkedNames" value="烏丸線">烏丸線
<input type="checkbox" v-model="checkedNames" value="尾西線">尾西線
<input type="checkbox" v-model="checkedNames" value="河和線">河和線
<input type="checkbox" v-model="checkedNames" value="知多新線">知多新線
<input type="checkbox" v-model="checkedNames" value="嵐山線">嵐山線
<input type="checkbox" v-model="checkedNames" value="小泉線">小泉線
<input type="checkbox" v-model="checkedNames" value="亀戸線">亀戸線
<input type="checkbox" v-model="checkedNames" value="蒲郡線">蒲郡線
<input type="checkbox" v-model="checkedNames" value="南港ポートタウン線">南港ポートタウン線
<input type="checkbox" v-model="checkedNames" value="羽島線">羽島線
<input type="checkbox" v-model="checkedNames" value="広見線">広見線
<input type="checkbox" v-model="checkedNames" value="特急スカイライナー">特急スカイライナー
<input type="checkbox" v-model="checkedNames" value="谷町線">谷町線
<input type="checkbox" v-model="checkedNames" value="北大阪急行線">北大阪急行線
<input type="checkbox" v-model="checkedNames" value="松浦鉄道線">松浦鉄道線
<input type="checkbox" v-model="checkedNames" value="中央線">中央線
<input type="checkbox" v-model="checkedNames" value="けいはんな線">けいはんな線
<input type="checkbox" v-model="checkedNames" value="駿豆線">駿豆線
<input type="checkbox" v-model="checkedNames" value="大雄山線">大雄山線
<input type="checkbox" v-model="checkedNames" value="北しなの線">北しなの線
<input type="checkbox" v-model="checkedNames" value="妙高はねうまライン">妙高はねうまライン
<input type="checkbox" v-model="checkedNames" value="グリーンライン">グリーンライン
<input type="checkbox" v-model="checkedNames" value="四つ橋線">四つ橋線
<input type="checkbox" v-model="checkedNames" value="津島線">津島線
<input type="checkbox" v-model="checkedNames" value="豊田線">豊田線
<input type="checkbox" v-model="checkedNames" value="上野東京ライン">上野東京ライン
<input type="checkbox" v-model="checkedNames" value="IRいしかわ鉄道線">IRいしかわ鉄道線
<input type="checkbox" v-model="checkedNames" value="あいの風とやま鉄道線">あいの風とやま鉄道線
<input type="checkbox" v-model="checkedNames" value="長堀鶴見緑地線">長堀鶴見緑地線
<input type="checkbox" v-model="checkedNames" value="日光線特急">日光線特急
<input type="checkbox" v-model="checkedNames" value="伊勢崎線特急">伊勢崎線特急
<input type="checkbox" v-model="checkedNames" value="東武スカイツリーライン">東武スカイツリーライン
<input type="checkbox" v-model="checkedNames" value="伊勢崎線">伊勢崎線
<input type="checkbox" v-model="checkedNames" value="日本海ひすいライン">日本海ひすいライン
<input type="checkbox" v-model="checkedNames" value="湯の山線">湯の山線
<input type="checkbox" v-model="checkedNames" value="中村･宿毛線">中村･宿毛線
<input type="checkbox" v-model="checkedNames" value="堺筋線">堺筋線
<input type="checkbox" v-model="checkedNames" value="生駒線">生駒線
<input type="checkbox" v-model="checkedNames" value="今津線">今津線
<input type="checkbox" v-model="checkedNames" value="西尾線">西尾線
<input type="checkbox" v-model="checkedNames" value="貝塚線">貝塚線
<input type="checkbox" v-model="checkedNames" value="和田岬線">和田岬線
<input type="checkbox" v-model="checkedNames" value="多摩川線">多摩川線
<input type="checkbox" v-model="checkedNames" value="竜ヶ崎線">竜ヶ崎線
<input type="checkbox" v-model="checkedNames" value="こどもの国線">こどもの国線
<input type="checkbox" v-model="checkedNames" value="世田谷線">世田谷線
<input type="checkbox" v-model="checkedNames" value="佐野線">佐野線
<input type="checkbox" v-model="checkedNames" value="七隈線">七隈線
<input type="checkbox" v-model="checkedNames" value="高師浜線">高師浜線
<input type="checkbox" v-model="checkedNames" value="富士急行線">富士急行線
<input type="checkbox" v-model="checkedNames" value="内子線">内子線
<input type="checkbox" v-model="checkedNames" value="琴平線">琴平線
<input type="checkbox" v-model="checkedNames" value="伊丹線">伊丹線
<input type="checkbox" v-model="checkedNames" value="鬼怒川線">鬼怒川線
<input type="checkbox" v-model="checkedNames" value="豊川線">豊川線
<input type="checkbox" v-model="checkedNames" value="郡中線">郡中線
<input type="checkbox" v-model="checkedNames" value="長尾線">長尾線
<input type="checkbox" v-model="checkedNames" value="甘木線">甘木線
<input type="checkbox" v-model="checkedNames" value="北九州モノレール">北九州モノレール
<input type="checkbox" v-model="checkedNames" value="近江鉄道線">近江鉄道線
<input type="checkbox" v-model="checkedNames" value="志度線">志度線
<input type="checkbox" v-model="checkedNames" value="高浜線">高浜線
<input type="checkbox" v-model="checkedNames" value="羽衣線">羽衣線
<input type="checkbox" v-model="checkedNames" value="桐生線">桐生線
<input type="checkbox" v-model="checkedNames" value="加太線">加太線
<input type="checkbox" v-model="checkedNames" value="小湊鐵道線">小湊鐵道線
<input type="checkbox" v-model="checkedNames" value="いすみ線">いすみ線
<input type="checkbox" v-model="checkedNames" value="真岡線">真岡線
<input type="checkbox" v-model="checkedNames" value="会津線">会津線
<input type="checkbox" v-model="checkedNames" value="阿武隈急行線">阿武隈急行線
<input type="checkbox" v-model="checkedNames" value="仙石東北ライン">仙石東北ライン
<input type="checkbox" v-model="checkedNames" value="大洗鹿島線">大洗鹿島線
<input type="checkbox" v-model="checkedNames" value="天理線">天理線
<input type="checkbox" v-model="checkedNames" value="動物園線">動物園線
<input type="checkbox" v-model="checkedNames" value="横河原線">横河原線
<input type="checkbox" v-model="checkedNames" value="小牧線">小牧線
<input type="checkbox" v-model="checkedNames" value="ニューシャトル">ニューシャトル
<input type="checkbox" v-model="checkedNames" value="御堂筋線">御堂筋線
<input type="checkbox" v-model="checkedNames" value="竹鼻線">竹鼻線
<input type="checkbox" v-model="checkedNames" value="観光列車">観光列車
<input type="checkbox" v-model="checkedNames" value="競馬場線">競馬場線
<input type="checkbox" v-model="checkedNames" value="桜通線">桜通線
<input type="checkbox" v-model="checkedNames" value="築港線">築港線
<input type="checkbox" v-model="checkedNames" value="御所線">御所線
<input type="checkbox" v-model="checkedNames" value="">
<input type="checkbox" v-model="checkedNames" value="宇野みなと線">宇野みなと線
<input type="checkbox" v-model="checkedNames" value="道南いさりび鉄道線">道南いさりび鉄道線
<input type="checkbox" v-model="checkedNames" value="桃太郎線">桃太郎線
<input type="checkbox" v-model="checkedNames" value="田原本線">田原本線
<input type="checkbox" v-model="checkedNames" value="金町線">金町線
<input type="checkbox" v-model="checkedNames" value="高野線汐見橋方面">高野線汐見橋方面
<input type="checkbox" v-model="checkedNames" value="気仙沼線BRT">気仙沼線BRT
<input type="checkbox" v-model="checkedNames" value="大船渡線BRT">大船渡線BRT
<input type="checkbox" v-model="checkedNames" value="男山ケーブル線">男山ケーブル線
<input type="checkbox" v-model="checkedNames" value="京津線">京津線
<input type="checkbox" v-model="checkedNames" value="石山坂本線">石山坂本線
<input type="checkbox" v-model="checkedNames" value="東豊線">東豊線
<input type="checkbox" v-model="checkedNames" value="井川線">井川線
<input type="checkbox" v-model="checkedNames" value="北勢線">北勢線
<input type="checkbox" v-model="checkedNames" value="上毛線">上毛線
<input type="checkbox" v-model="checkedNames" value="大井川本線">大井川本線
<input type="checkbox" v-model="checkedNames" value="小湊鉄道線">小湊鉄道線
<input type="checkbox" v-model="checkedNames" value="湊線">湊線
<input type="checkbox" v-model="checkedNames" value="貴志川線">貴志川線
<input type="checkbox" v-model="checkedNames" value="三岐線">三岐線
<input type="checkbox" v-model="checkedNames" value="四日市あすなろう鉄道線">四日市あすなろう鉄道線
<input type="checkbox" v-model="checkedNames" value="上高地線">上高地線
<input type="checkbox" v-model="checkedNames" value="上信線">上信線
<input type="checkbox" v-model="checkedNames" value="養老線">養老線
<input type="checkbox" v-model="checkedNames" value="西信貴鋼索線">西信貴鋼索線
<input type="checkbox" v-model="checkedNames" value="妙見の森ケーブル">妙見の森ケーブル
<input type="checkbox" v-model="checkedNames" value="名城線･名港線">名城線･名港線
<input type="checkbox" v-model="checkedNames" value="京阪本線">京阪本線
<input type="checkbox" v-model="checkedNames" value="鴨東線">鴨東線
<input type="checkbox" v-model="checkedNames" value="中之島線">中之島線
<input type="checkbox" v-model="checkedNames" value="渥美線">渥美線
<input type="checkbox" v-model="checkedNames" value="京都本線">京都本線
<input type="checkbox" v-model="checkedNames" value="郊外電車">郊外電車
<input type="checkbox" v-model="checkedNames" value="銚子電気鉄道線">銚子電気鉄道線
<input type="checkbox" v-model="checkedNames" value="こうや">こうや
<input type="checkbox" v-model="checkedNames" value="泉北ライナー">泉北ライナー
<input type="checkbox" v-model="checkedNames" value="阿佐東線">阿佐東線
<input type="checkbox" v-model="checkedNames" value="多奈川線">多奈川線
<input type="checkbox" v-model="checkedNames" value="神戸本線">神戸本線
<input type="checkbox" v-model="checkedNames" value="樽見線">樽見線
<input type="checkbox" v-model="checkedNames" value="宝塚本線">宝塚本線
<input type="checkbox" v-model="checkedNames" value="信貴線">信貴線
<input type="checkbox" v-model="checkedNames" value="道明寺線">道明寺線
<input type="checkbox" v-model="checkedNames" value="伊賀線">伊賀線
<input type="checkbox" v-model="checkedNames" value="石川線">石川線
<input type="checkbox" v-model="checkedNames" value="浅野川線">浅野川線
<input type="checkbox" v-model="checkedNames" value="交野線">交野線
<input type="checkbox" v-model="checkedNames" value="宇治線">宇治線
<input type="checkbox" v-model="checkedNames" value="武庫川線">武庫川線
<input type="checkbox" v-model="checkedNames" value="甲陽線">甲陽線
<input type="checkbox" v-model="checkedNames" value="湘南モノレール">湘南モノレール
<input type="checkbox" v-model="checkedNames" value="明知線">明知線
<input type="checkbox" v-model="checkedNames" value="弘南線">弘南線
<input type="checkbox" v-model="checkedNames" value="大鰐線">大鰐線
<input type="checkbox" v-model="checkedNames" value="北海道新幹線">北海道新幹線
<input type="checkbox" v-model="checkedNames" value="島原鉄道線">島原鉄道線
<input type="checkbox" v-model="checkedNames" value="南阿蘇鉄道線">南阿蘇鉄道線
<input type="checkbox" v-model="checkedNames" value="水島臨海鉄道線">水島臨海鉄道線
<input type="checkbox" v-model="checkedNames" value="生駒鋼索線">生駒鋼索線
<input type="checkbox" v-model="checkedNames" value="今里筋線">今里筋線
<input type="checkbox" v-model="checkedNames" value="金沢シーサイドライン">金沢シーサイドライン
<input type="checkbox" v-model="checkedNames" value="飯坂線">飯坂線
<input type="checkbox" v-model="checkedNames" value="別所線">別所線
<br><br>
<h2>利用路線：{{this.checkedNames}}</h2>
<p><button @click="hozon">上記設定をサーバーに保存</button></p>
<p><button @click="back">保存せず１つ前の画面へ戻る</button></p>
  </div>
</template>

<script>
import {db} from '../plugins/firebase';
import firebase from 'firebase'
import { EnhancedCheck } from 'vue-enhanced-check'
  export default {
    components: { EnhancedCheck },
    name: 'etc',
    data() {
      return {
        myset: "",
        checkedNames: []
      }
    },
  created() {
    if(this.$store.state.signflag == 0){
  alert("ログインしていません")
  this.$router.push('/sign')
}
  },
  methods: {
    hozon() {
        db.collection('user').doc(this.$store.state.uid).collection('rosen').doc('rosen').set({
        area:"etc",
         rosen: this.checkedNames
          })
        alert("保存しました")
        this.$router.push('/conf')
    },
     back() {
       this.$router.push('/conf')
     }
  }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1,
  h2 {
    font-weight: normal;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display: inline-block;
    margin: 0 10px;
  }
  a {
    color: #42b983;
  }
    .hello{
    text-align:center;
  }
</style>
