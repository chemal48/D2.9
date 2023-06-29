# D2.9
Команды Shell

1. Создание нового пользователя: u1 = User.objects.create_user('username');
2. Создание нового объекта класа Author: Author.objects.create(authorUser=u1);
3. Создание новой категории(доступны IT, kitchen, science, cars): Category.objects.create(name='NameCategory);
4. Создание нового поста: Post.objects.create(author=author1, categoryTipe='тип категории', title='sometitle', text='sometext';
5. Добавление категорий: Post.objects.get(id=поста/новости).postCategory.add(Category.objects.get(id=категории));
6. Создание коментариев: Comment.objects.create(commentPost=Post.objects.get(id=1), commentUser=Author.objects.get(id=автора).authorUser, text='sometextofcomments')
Второй вариант написания: Comment.objects.create(commentPost=Post.objects.get(id=поста), commentUser=User.objects.get(id=пользователя), text='sometextofcomments') 
7. Применение функций like() и dislike() к комментариям: Comment.objects.get(id=комментария).like() / Comment.objects.get(id=комментария).dislike();
Применение функций like() и dislike() к постам: Post.objects.get(id=поста).like() / Post.objects.get(id=поста).dislike();
8. Обновление рейтинга пользователей: Author.objects.get(id=автора).update_rating();
9. Вывод username и рейтинг лучшего пользователя: a = Author.objects.order_by('-ratingAuthor')[:1]
						  for i in a:
							i.authorUser.username
							i.ratingAuthor
							
10. Вывод даты добавления, username автора, райтинг, заголовок и превью лучшей статьиБ основываясь на рейтинге: 
 t = Post.objects.order_by('rating')[:1]
	for i in t:
	     i.dateCreation
	     i.author.authorUser.username
	     i.rating
	     i.title
	     i.preview()
11. Вывести все комментарии (дата, пользователь, рейтинг, текст) к этой статье:
com = Comment.objects.get(commentPost=Post.objects.get(id=статьи))
com.dateCreation
com.commentUser
com.rating
com.commentPost.text
