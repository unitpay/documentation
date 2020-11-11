# InSales

**Добавление проекта:**

1. На шаге 2 "Подтверждение и завершение" рекомендуем выбрать вариант мета-тег:  


   ​![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-M9Y_k8Gr-WxeECFRelw%2F-MFFC1Q-x239zjUIxsx4%2F-MFFD3_Y8r81f1D4A0Rw%2Fimage.png?alt=media&token=e1a62e62-4569-49ca-8445-b0feea7c160d)  
   ​

2. В ЛК insales зайти в “Настройки“ =&gt; “Настройки сайта” =&gt; “Счётчики и коды”. 
3. Добавить код в поле “JavaScript-код для вывода на всех страницах магазина“.

   ​![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-M9Y_k8Gr-WxeECFRelw%2F-MFFC1Q-x239zjUIxsx4%2F-MFFDfkhR_BKdAd5-FY8%2Fimage.png?alt=media&token=c6f7d485-ae61-4bfc-aab8-11cae32411a7)

**Инструкция для интеграции оплаты через систему Unitpay.**

1. Зайдите на страницу "Настройки" в панели администратора InSales.

2. Выберите в меню пункт "Оплата".

3. На странице "Виды оплаты" создайте новый вид оплаты, выбрав в выпадающем списке пункт "Внешний способ оплаты" и нажав кнопку "Добавить".

4. В поле "Идентификатор магазина" введите PUBLIC KEY вашего проекта в Unitpay.

5. В поле "Пароль" введите SECRET KEY вашего проекта в Unitpay.

6. В поле "URL" внешнего сервиса введите https://unitpay.money/insales.

7. Для формирования чеков требуется поставить галку напротив "Передавать детальную информацию о заказе" \(Если подключена онлайн-касса через Unitpay\).

8. Сохраните страницу.

9. Перейдите в панель управления проектом в Unitpay.

10. В поле "URL" раздела "Обработчик платежей" введите https://unitpay.money/insales/handler.

11. Сохраните настройки проекта.

**Интеграция завершена. По всем вопросам вы можете обращаться к своему персональному менеджеру или в круглосуточный чат-виджет Юнит.Помощь!**
