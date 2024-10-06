---
title: 贪吃蛇代码
date: 2024-10-06 23:34:00 +0800
categories: [随笔]
tags: [生活]
pin: true
author: 理性暗面

toc: true
comments: true
typora-root-url: ../../lixanm.github.io
math: false
mermaid: true

image:
  src:
  alt: 

---

# 感谢关注～ 

```cpp
#include<graphics.h>
#include<stdio.h>
#include<conio.h>//控制键盘
#define WIDE 640
#define HIGH 480
#define MAX_snake 64*48

//定义蛇的每节身体
struct Pos
{
	int x;
	int y;
	DWORD color;
};
//定义蛇
struct Snake
{
	int num;//身体的节数
	int dir;//方向
	int score;//分数
	int size;//宽和高
	int speed;//蛇的速度
	struct Pos coor[MAX_snake];//每一节身体

}snake;
//定义食物
struct Food
{
	int x;
	int y;
	DWORD color;
	bool flag;//是否被吃 是true 否false
}food;

//枚举
enum DIR
{
	UP,
	DOWN,
	LEFT,
	RIGHT
};
//初始化数据
void GameInit()
{
	//蛇的身体随机变化
	srand(GetTickCount());

	snake.num = 3;
	snake.dir = RIGHT;
	snake.score = 0;
	snake.size = 10;
	snake.speed = 10;

	for (int i = 0; i < 3; i++)
	{
		snake.coor[i].x = 20 - i * 10;
		snake.coor[i].y = 0;
		snake.coor[i].color = RGB(rand() % 256, rand() % 256, rand() % 256);
	}

	//初始化食物
	food.x = rand() % (WIDE / 10) * 10;
	food.y = rand() % (HIGH / 10) * 10;
	food.color = RGB(rand() % 256, rand() % 256, rand() % 256);
	food.flag = true;
}
//画蛇   画食物
void GameDraw()
{
	cleardevice();//刷新游戏窗口
	for (int i = 0; i < snake.num; i++)
	{
		setfillcolor(snake.coor[i].color);//颜色
		fillrectangle(snake.coor[i].x, snake.coor[i].y, snake.coor[i].x + 10, snake.coor[i].y + 10);//画矩形，蛇就是矩形

	}

	//绘制食物
	if (food.flag)
	{
		setfillcolor(food.color);
		solidellipse(food.x, food.y, food.x + 10, food.y + 10);

	}

	//绘制分数
	char temp[20] = "";
	sprintf(temp, "分数：%d", snake.score);
	outtextxy(10,10,temp);
}

//让蛇动起来
void GameMove()
{
	for (int i = snake.num - 1;i>0; i--)
	{
		snake.coor[i].x = snake.coor[i - 1].x;
		snake.coor[i].y = snake.coor[i - 1].y;
	}

	switch (snake.dir)
	{
	case UP:
		snake.coor[0].y -= snake.speed;
		break;
	case DOWN:
		snake.coor[0].y += snake.speed;
		break;
	case LEFT:
		snake.coor[0].x -= snake.speed;
		break;
	case RIGHT:
		snake.coor[0].x += snake.speed;
		break;
	}

}
//用键盘控制
void GameController()
{
	//获取键盘
	char key = _getch();

	switch (key)
	{
	case 72:case 'W':
		if(snake.dir!=DOWN)
		snake.dir = UP;
		break;
	case 80:case 'S':
		if (snake.dir != UP)
		snake.dir = DOWN;
		break;
	case 75:case 'A':
		if (snake.dir != RIGHT)
		snake.dir = LEFT;
		break;
	case 77:case 'D':
		if (snake.dir != LEFT)
		snake.dir = RIGHT;
		break;
	}
	printf("%d\n", key);
}
//创建一个新的食物
void createFood()
{
	if (!food.flag)
	{
		food.x = rand() % (WIDE / 10) * 10;
		food.y = rand() % (HIGH / 10) * 10;
		food.color = RGB(rand() % 256, rand() % 256, rand() % 256);
		food.flag = true;
	}
}
//吃到食物
void EatFoot()
{
	if (food.flag && snake.coor[0].x == food.x && snake.coor[0].y == food.y)
	{
		//吃到了
		food.flag = false;
		snake.num++;
		snake.score += 10;
		snake.coor[snake.num - 1].color = RGB(rand() % 256, rand() % 256, rand() % 256);

		//创建一个新的食物
		createFood();

	}
}
//碰到自己
void SnakeSnake()
{
	for (int i = 1; i <= snake.num-1; i++)
	{
		if (snake.coor[0].x == snake.coor[i].x && snake.coor[0].y == snake.coor[i].y)
			exit(0);
	}
}

//碰到墙
void SnakeQiang()
{
	if (snake.coor[0].x == -1)snake.coor[0].x = WIDE - 1;
	if (snake.coor[0].x == WIDE)snake.coor[0].x = 0;
	if (snake.coor[0].y == -1)snake.coor[0].y = HIGH - 1;
	if (snake.coor[0].y == HIGH)snake.coor[0].y = 0;
}


//程序入口
int main()
{
	initgraph(WIDE,HIGH,1);//创建窗口
	setbkcolor(RGB(207,214,229));//设置背景颜色
	cleardevice();//刷新游戏窗口


	GameInit();//初始化

	//fillcircle(20,20,20);
	while (true)
	{
		GameDraw();//绘制
		GameMove();

		BeginBatchDraw();//双缓存机制，解决闪屏问题

		if (_kbhit())//检测到按键
		{
			GameController();//用键盘控制
		}

		FlushBatchDraw();//刷新屏幕

		SnakeQiang();
		SnakeSnake();
		EatFoot();
		Sleep(100);

	}
}
```





