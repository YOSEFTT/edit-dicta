# [הגדרת כותרות לאוצריא](הגדרת_כותרות_לאוצריא.py)
ב'נתיב הקובץ' בוחרים את הקובץ עליו עובדים, ב'מילה לחפש' בוחרים את המילה אותה אתם רוצים להגדיר ככותרת, כל ספר לפי ענינו, לדוג: פרק/סימן/סעיף/פסוק/הלכות/וכדו' ע"ז הדרך.
'מספר סימן מקסימלי' הכוונה כפשוטו, כרגע הוא מוגדר ברירת מחדל על המקסימום שלו הוא 999, יותר מזה אין תמיכה כרגע לע"ע.
ו'רמת כותרת' כפשוטה, שם הספר הוא תמיד כותרת רמה 1. וזה כבר מוגדר בכל ספרי דיקטה אין צורך לגעת בזה.

ולדוגמא, בדר"כ בספר על התורה, אז חומש... זה כותרת רמה 2, פרק... זה כותרת רמה 3, פסוק... זה כותרת רמה 4, ואם גם בתוך כל פסוק ופסוק יש חלוקה נוספת אז זה יהי' כותרת רמה 5, וכן הלאה.
שים לב! התוכנה מחפשת את המילה שבחרת, רק אם התמלאו 2 תנאים.
א, שהיא בתחילת שורה, דהיינו שיש אנטר לפני'.
ב, שיש אחרי' מילה בעלת ערך מספרי או לפי כללי הגימטרי', דהיינו סימן א, או סימן ראשון וכדו', אבל אם כתוב סימן בענייני.... אז הוא לא התייחס לזה כלל וידלג ע"ז.
# שינוי רמת כותרת
קורה לפעמים שעושים רמת כותרת מסוימת, ואז מחליטים שצריך לעשות על איזה משהו אחר רמת כותרת יותר גבוהה,
לדוגמא, עשית על כל הדפים כותרת רמה 2, ואז אתה רוצה לעשות כותרות לפרקים, וממילא הפרקים אמורים להיות רמה 2 והדפים רמה 3.
אז התוכנה הבאה נועדה להחליף רמות כותרות [היא מחליפה בגוף הקובץ].
כמו"כ בהרבה ספרים, יש פסקאות מדי ארוכות, ומכיון שבדר"כ בסוף כל קטע בספרים הישנים יש נקודותיים, אז התוכנה הבאה מחליפה את הנקודותיים ורווח בנקודותיים ואנטר.
[אם יש נקודותיים, רווח, ואנטר, הוא לא מחליף כדי שלא יהי' 2 אנטרים]
# החלפת כותרות לעמוד ב גירסא 3
בהרבה ספרים שעל הש"ס, כתוב כך:
דף ב' ע"א
אבגדהוזחטי
ע"ב
אבגדהוזחטי

ואז אם תריצו את התוכנה או הסקריפט על המילה 'דף', יהי' לכם רק את הדפים.
אמנם אפשר להחליף את כל אנטר וע"ב ב- אנטר ועמוד ב, ואז להריץ את התוכנה על המילה 'עמוד', אבל אז יצא לנו כותרת של דף ב, ואח"כ כותרת של עמוד ב, וכן הלאה.
ע"מ לפתור את הבעי' הזו, התוכנה הבאה לוקחת את תוכן הכותרת הקודמת, ומוסיפה אותה לכותרת הבאה, וכך יצא - דף ב:

עדכון:
התוכנה עודכנה, היא מאפשרת לבחור האם הכותרות יהפכו ל - דף X :, לדוגמא דף ב:
או ל - דף X ע"ב, לדוגמא - דף ב ע"ב
# הוספת מספר עמוד בכותרת הדף
למקרה שהקובץ נראה כך:
<h2>דף ב</h2>
<b>עמוד א</b> טקסט כלשהוא
<h5>דף ג</h5>
ע"א, טקסט כלשהוא
<h3>דף ד</h3>
עמוד ב. טקסט כלשהוא
<h3>דף ז</h3>
<b>ע"ב</b> טקסט כלשהוא

הוא מחליף ל:
<h2>דף ב.</h2>
טקסט כלשהוא
<h5>דף ג.</h5>
טקסט כלשהוא
<h3>דף ד:</h3>
טקסט כלשהוא
<h3>דף ז:</h3>
טקסט כלשהוא

ניתן במקום זה להחליף למילים דף ב ע"א, דף ד ע"ב,
יש חלון שניתן להגדיר בו מה מעוניינים.
# הדגשת מילה ראשונה וניקוד בסוף קטע
א, כותב נקודה או נקודותיים [לבחירת המשתמש] בסוף קטע שאין בו נקודה (אם הוא לא מודגש, ולא כתב גדול ולא קטן, ויש בו מעל 10 מילים, כדי שלא יעשה ניקוד גם בשורה המוגדרת ככותרת).
ב, מדגיש כל מילה ראשונה בכל קטע, אם היא לא מוגדרת ככותרת, ולא כתב גדול או קטן.
ניתן לבחור רק אחד מהפעולות.
# בדיקת תגים
יוצר כותרות לאותיות שאין לפניהם מילה כלשהיא כגון פרק/סימן/שאלה וכדו', אלא רק א ב ג וכו'.
הסקריפט עובד רק על אותיות שיש בהם משמעות מספרית ע"פ כללי הגימטרי', כדי שלא יווצרו בטעות כותרות שאינם נכונות.
יש לבחור בממשק הגרפי את הצורה המדויקת בה מופיעים האותיות בקובץ שאתם עובדים עליו, כגון א: א, או א. או א' וכדו'.
# יצירת כותרות לעמוד ב
יצירת כותרות ל'עמוד ב'.
עד עכשיו הי' רק את התוכנה להחלפת כותרות של 'עמוד ב', לכותרות עם שם הדף האמיתי, דהיינו שאם כבר יש כותרת שנקראת 'עמוד ב', אז הוא מחליף אותה לכותרת עם שם הדף+הסימון לעמוד ב.
אבל כל זה הוא רק אם ה'עמוד ב' מוגדר כבר ככותרת, ובשביל זה באה התוכנה הזו להגדיר וליצור בכל מקום שכתוב במסמך בתחילת שורה את המילים 'עמוד ב', בין אם יש לפניהם ולאחריהם וביניהם כל מיני תגים מסוימים, וכן גם אם כתוב: 'שם עמוד ב' וכדו', בכל אלה תיווצר כותרת שנקראת - 'עמוד ב', ואחר"כ יש להריץ את התוכנה שנקראת החלפת כותרות ל'עמוד ב'.
