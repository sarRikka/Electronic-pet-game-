# Electronic-pet-game-
C++入门（小黑窗文字宠物游戏）

                         电子宠物游戏

设计一款文字式交互电子宠物游戏，该游戏要求具备如下要素：

一、玩家（Player），玩家具备如下要素：
体力：体力是玩家行动的关键要素，玩家最高拥有100点体力值，每种不同行动都会消耗体力，一旦体力归0，玩家只能选择休息恢复体力。

金钱：金钱是购买宠物道具的要素，金钱可以通过打工获取。

行动：玩家可以在一个时间点选择一个行动，每种行动均会获取一定内容并且消耗当前时间：

1)打工，打工会消耗玩家体力，收获金钱，消耗时间。
家教，消耗2个时间，获取50金钱，消耗30体力
麦当劳兼职，消耗个4时间，获取120金钱，消耗70体力
割草，消耗1个时间，获取20金钱，消耗20体力
请你设计。


2)购买宠物粮食，玩家消耗1个时间，20体力，根据具体宠物粮食消耗金钱。

3)喂食：玩家消耗1个时间，20体力。

4)休息，玩家消耗1个时间，恢复50体力。

5)和宠物玩耍：玩家消耗1个时间，50体力。

6)清洗宠物：玩家消耗1个时间，30体力。

7)每天结束时，玩家会进入睡眠状态，睡眠会恢复玩家全部体力，并进入下一天。


二、宠物（Pet），当前电子系统仅支持宠物猫（Cat）和宠物狗（Dog）两种宠物，但是系统必须拥有扩展宠物的能力，宠物具备如下要素：

性别：公/母

饱食度：宠物的饱食度为0时，会降低10点愉悦度，猫会降低1斤体重，狗会降低2斤体重。宠物饱食度为100时，猫会提高1斤体重，狗会提高2斤体重。宠物被喂食会根据投喂的食物提高一定饱食度。宠物玩耍后会根据玩耍和宠物自身情况降低饱食度。

愉悦度：愉悦度影响宠物对玩家的态度，愉悦度为0时，宠物会离开主人；愉悦度低于30时，宠物不会和主人玩耍；愉悦度低于70时，宠物狗不会让主人清洗；宠物猫的愉悦度必须90以上，才会让主人清洗。

体重：体重是衡量宠物的健康，公猫健康体重为8~12斤，初始时公猫为10斤，母猫健康体重为4~8斤，初始时母猫为6斤。公猫体重低于4斤，高于16斤将会因为健康不佳死亡，母猫体重低于2斤，高于10斤将会因为健康死亡。狗健康体重为30~60斤，初始时狗会有45斤体重。低于15斤，高于75斤，狗会因为健康死亡。宠物低于超出健康体重时，每个时间段都会降低10点愉悦度。

清洁度：清洁度为0时，宠物愉悦度每个时间段降低30，清洁度高于80时，宠物愉悦度每个时间段升高10。

宠物行为：
1)玩耍：宠物狗玩耍时，会消耗40点饱食度，提高70点愉悦度，降低10点清洁度。宠物猫玩耍时，会消耗20点饱食度，提高30点愉悦度（猫是高冷的），降低10点清洁度。

2)叫：狗是汪汪叫，猫是喵喵叫（这里只需要printf信息表示即可）

3)喂食：消耗1个时间，喂食时，宠物会先叫，然后会根据提供食物不同获取属性。

4)猫的自洁：猫有30%的可能性进行自洁，消耗1个时间，提高30清洁度；

5)猫的随机抓老鼠：在任何时间段，猫有20%的可能会去抓老鼠，此时主人是无法对猫进行交互的。消耗1个时间，如果此时猫的饱食度低于50，会吃掉老鼠，提高40饱食度，降低30清洁度，提高5愉悦度。如果此时猫的饱食度大于等于50，猫只会玩耍老鼠，降低20饱食度，降低10清洁度，提高40愉悦度。

6)被主人清洁：消耗1个时间，提高100清洁度。但是对于猫，清洁度高于80或清洁间隔低于30个时间段时，不接受被主人清洁，强行清洁会降低50愉悦度（猫主子不喜欢）

7)非主人交互时间：该时间段一般为主人买东西、打工或休息等无暇顾及宠物的时间段，该时间段内宠物将降低20饱食度，另外，狗降低20点愉悦度，和20点清洁度。猫不会降低愉悦度，但是会降低5清洁度。

8)每天结束时，宠物会强制进入休息，提高30愉悦度，降低5清洁度，降低60饱食度。

三、宠物食物
粗糙的粮食：花费30金钱，为宠物提供30体力，10愉悦度，降低15清洁度；
精品粮食：花费60金钱，为宠物提供50体力，40愉悦度，降低5清洁度；
香肠：花费20金钱，为宠物提供20体力，30愉悦度，降低20清洁度；
其他可自行设计


四、系统
游戏开始时，系统给予玩家选择宠物和宠物性别的机会

一天提供7个时间段给玩家选择行动方案，一旦玩家选择并确定某种行动方案，视作时间段开始，此时，时间会发生对应的流逝。每个时间段开始前，系统必须显示当时玩家和宠物的状态。

一旦宠物死亡，游戏结束。三十天后，宠物依然健康，游戏结束，并结算显示宠物状态。

系统提供存档、读档、关闭、重新开始等功能

效果图如下：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200705000640244.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzYmJ2,size_16,color_FFFFFF,t_70)![在这里插入图片描述](https://img-blog.csdnimg.cn/20200705000831813.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzYmJ2,size_16,color_FFFFFF,t_70)


源码如下(可直接运行)


```cpp
#include<iostream>
#include<vector>
#include<string>
#include<fstream>
#include<sstream>
#include<iomanip>
#include<map>
#include<algorithm>
#include<stdio.h>
#include<time.h>

#define random(x) (rand()%x)
using namespace std;

typedef struct//存储文档数据的结构体
{
	string sort;
	int day;
	int strength, money, time;
	map<string, int> foods;
	string sex;
	int satiety;
	int happiness;
	int cleanliness;
	int weight;
}datas;


//全部类的声明
class player;
class pet;
class cat;
class dog;


void interactCat(cat& pe, player& pl, int day);      //player类与cat类的交互函数
void interactdog(dog& pe, player& pl, int day);      //player类与dog类的交互函数
void getData(const string& filename, datas& data);   //文档的读取函数
void putData(const string& filename, datas data);    //文档的存储函数
void adopt();                                        //开始新的游戏函数
void continueAdopt(datas da);                        //接着之前的存储继续游戏函数



class food
{
private:
	string name;              //食物的名字
	int payMoney;			  //购买食物所花费的金钱
	int addStrength;          //吃掉食物所补充的体力
 	int addHappiness;         //吃掉食物所增加的愉悦度
	int reduceCleanliness;    //吃掉食物所减少的清洁度
public:
	food(string n, int p, int as, int ah, int rc) :name(n), payMoney(p),
		addStrength(as), addHappiness(ah), reduceCleanliness(rc) {};
	string getName() { return name; };
	int getPayMoney() { return payMoney; };
	int getAddStrength() { return addStrength; };
	int getAddHappiness() { return addHappiness; };
	int getReduceCleanliness() { return reduceCleanliness; };
};

food petfood[5] =//食物列表
{
	{"粗糙的粮食",30,30,10,15},
	{"精品粮食",60,50,40,5},
	{"香肠",20,20,30,20},
	{"辣条",10,20,5,30},
	{"老八秘制小汉堡",28,66,-30,66}
};

class player
{
private:
	int strength, money, time;   //玩家的体力、金钱和时间
	map<string, int> foods;      //玩家所拥有的食物
public:
	player(int s = 100, int m = 100, int t = 7, map<string, int> food = {}) :strength(s), money(m), time(t) {};
	int getTime() { return time; };
	int getStrength() { return strength; };
	int getMoney() { return money; };
	map<string, int> getFoods() {return foods; };
	void show();                 //显示玩家状态的函数
	int teach();                 //家教的函数
	int kfc();                   //麦当劳打工的函数
	int cutGrass();              //除草的函数
	int buyFood();               //购买食物的函数
	int feed();                  //喂养宠物的函数
	void relax();                //休息的函数
	int playWithPet();           //和宠物玩耍的函数
	int cleanPet();              //给宠物清洁的函数
	void sleep();                //睡眠的函数
	void change();               //状态调整的函数
	void foodGet(const map<string, int> f);//取出食物用于存档的接口函数
};

void player::foodGet(const map<string, int> f)
{
	foods = f;
}

void player::change()
{
	if (strength >= 100) strength = 100;//当状态值超出上限或下限，调整为上限或下限值。
	if (strength <= 0) strength = 0;
}

void player::show()
{
	cout <<"玩家的属性值："<< "strength:" << strength << "  money:" << money << "  time" << time << endl<<endl;
}

int player::teach()    //若返回1则条件满足，成功执行操作，下同
{
	int flag = 1;
	if (time >= 2)     //判断时间是否足够，下同
	{
		if (strength >= 30)    //判断体力是否足够，下同
		{
			time -= 2;
			money += 50;
			strength -= 30;
		}
		else
		{
			cout << "体力不足" << endl;
			flag = 0;
		}

	}
	else cout << "今天时间不够了" << endl << endl;
	return flag;

}

int player::kfc()
{
	int flag = 1; 
	if (time >= 4)
	{
		if (strength >= 70)
		{
			time -= 4;
			money += 120;
			strength -= 70;
		}
		else
		{
			cout << "体力不足" << endl;
			flag = 0;
		}
	}
	else cout << "今天时间不够了" << endl << endl;
	return flag;
}

int player::cutGrass()
{
	int flag = 1;
	if (time >= 1)          
	{

		if (strength >= 20)
		{
			time--;
			money += 20;
			strength -= 20;
		}
		else
		{
			cout << "体力不足" << endl;
			flag = 0;
		}
	}
	else cout << "今天时间不够了" << endl << endl;
	return flag;
}

int player::buyFood()
{
	int flag = 1;
	if (strength >= 20)
	{
		time--;
		strength -= 20;
		system("cls");                   //进行清屏，下同
		cout << "哈喽~  " << endl << endl
			<< "欢迎光临小店！" << endl<<endl
			<< "以下是食物清单~" << endl<<endl
			<< "1号食物《粗糙的粮食》所需金钱：30  增加的体力：30  增加愉悦度：10 减少清洁度：15" << endl << endl
			<< "2号食物《精品粮食》所需金钱 60  增加的体力：50  增加愉悦度：40  减少清洁度：5" << endl << endl
			<< "3号食物《香肠》所需金钱 20  增加的体力：20  增加愉悦度：30  减少清洁度：20" << endl << endl
			<< "4号食物《辣条》所需金钱 10  增加的体力：20  增加愉悦度：5  减少清洁度：30" << endl << endl
			<< "5号食物《老八秘制小汉堡》所需金钱 28  增加的体力：66  增加愉悦度：-30  减少清洁度：6<<6" << endl << endl
			<< "**请输入所要购买食物的序号**" << endl << endl;
		int sec;
		cin >> sec;     //选择食物
		money -= petfood[sec - 1].getPayMoney();          //根据购买的食物减少金钱
		foods[petfood[sec - 1].getName()]++;              //把购买的食物存入
	}
	else
	{
		cout << "体力不足" << endl;
		flag = 0;
	}
	return flag;
}

int player::feed()
{	
	time--;
	strength -= 20;
	int flag=0;
	system("cls");
	cout << "有如下食物" << endl << endl;
	for (map<string, int>::iterator i = foods.begin(); i != foods.end(); i++)
	{
		if (i->second >= 1)
		{
			cout << i->first << ":" << i->second << endl << endl;
			flag = 1;
		}
	}
	if (flag == 0)
	{
		cout << "你没有食物！" << endl << endl;
		cout << "输入任意键按回车返回：";
		cin >> flag;
		return -1;
	}
	else
	{
		cout << "选择喂食食物：(《-请看清你有哪些食物，再进行喂食！)" << endl << endl
			<< "1号食物《粗糙的粮食》增加的体力：30  增加愉悦度：10 减少清洁度：15" << endl << endl
			<< "2号食物《精品粮食》增加的体力：50  增加愉悦度：40  减少清洁度：5" << endl << endl
			<< "3号食物《香肠》增加的体力：20  增加愉悦度：30  减少清洁度：20" << endl << endl
			<< "4号食物《辣条》增加的体力：20  增加愉悦度：5  减少清洁度：30" << endl << endl
			<< "5号食物《老八秘制小汉堡》增加的体力：66  增加愉悦度：-30  减少清洁度：66" << endl << endl;
		int sec;
		cin >> sec;
		foods[petfood[sec - 1].getName()]--;
		return sec - 1;              //返回喂食的食物序号给宠物
	}

}

void player::relax()
{
	time--;
	strength += 50;
	if (strength > 100) strength = 100;
}

int player::playWithPet()
{
	int flag=1;
	if (strength >= 20)
	{
		time--;
		strength += 50;
	}
	else
	{
		cout << "体力不足" << endl;
		flag = 0;
	}
	return flag;

}

int player::cleanPet()
{
	int flag = 1;
	if (strength >= 20)
	{
		time--;
		strength -= 30;
	}
	else
	{
		cout << "体力不足" << endl;
		flag = 0;
	}
	return flag;
}

void player::sleep()
{
	time = 7;
	strength = 100;
}



class pet                   //该类为抽象类，用作cat类和dog类的基类
{
protected:
	string sex;             //宠物的性别
	int satiety;            //宠物的饥饿度
	int happiness;          //宠物的愉悦度
	int cleanliness;        //宠物的清洁度   
	int weight;             //宠物的体重
public:
	pet(string s = "无", int sa = 0, int ha = 0, int cl = 0, int we = 0) :
		sex(s), satiety(sa), happiness(ha), cleanliness(cl), weight(we) {};
	string getSex() { return sex; };
	int getSatiety() { return satiety; };
	int getHappiness() { return happiness; };
	int getCleanliness() { return cleanliness; };
	int getWeight() { return weight; };
	virtual void change()=0;           //宠物根据自身属性，一个时间段的属性变化函数（为纯虚函数，下同）
	virtual void show()=0;             //宠物的显示属性函数
	virtual void play()=0;             //宠物的玩耍函数
	virtual void shout() = 0;          //宠物的嚎叫函数
	void eat(int sec);                 //宠物的进食函数
	virtual void cleanByBoss() = 0;    //宠物被主人清洁函数
	virtual void unInterract() = 0;    //宠物非交互事件段状态改变函数
	virtual int death() = 0;           //宠物的死亡函数
	void balance();                    //宠物根据上限与下限的调整函数
	void dayEnd();                     //宠物进入新的一天的状态改变函数
};

void pet::balance()
{
	if (happiness >= 100) happiness = 100;
	if (happiness <= 0) happiness = 0;
	if (satiety >= 100) satiety = 100;
	if (satiety <= 0) satiety = 0;
	if (cleanliness >= 100) cleanliness = 100;
	if (cleanliness <= 0) cleanliness = 0;
}

void pet::eat(int sec)
{
	if(sec!=-1)           //sec为-1是主人条件不满足的情况，不能进行喂食
	{
		satiety += petfood[sec].getAddStrength();
		cleanliness -= petfood[sec].getReduceCleanliness();
		happiness += petfood[sec].getAddHappiness();
	}

}

void pet::dayEnd()
{
	happiness += 30;
	cleanliness -= 5;
	satiety -= 60;
}

class cat :public pet
{
public:
	cat(string s = "无", int sa = 0, int ha = 0, int cl = 0, int we = 0) :pet(s, sa, ha, cl, we) {};
	virtual void show();        //对纯虚函数进行重载，下同
	virtual void play();
	virtual void shout();
	virtual void change();
	virtual void cleanByBoss();
	virtual void unInterract();
	virtual int death();
	void cleanMyself();
	int catchMouse();
};
/*string sex;
	int satiety;
	int happiness;
	int cleanliness;
	int weight;*/
void cat::show()
{
	cout << "你可爱的小" << getSex() << "猫" << ":" << "属性值如下："
		<< " 饱食度：" << getSatiety() << " 愉悦度：" << getHappiness()
		<< " 清洁度：" << getCleanliness() << " 体重：" << getWeight() << endl << endl;
}

void cat::play()
{
	if (happiness >= 30)
	{
		satiety -= 20;
		happiness += 30;
		cleanliness -= 10;
	}
	else
	{
		cout << "愉悦度不够，猫主子不想洗" << endl << endl;
	}
}

void cat::shout()
{
	cout << "喵喵~~  喵~ 喵~ 喵~ " << endl << endl;
}

void cat::cleanMyself()
{
	srand((int)time(0));                 //对猫有概率自洁的判断
	if(random(10)<=2)	cleanliness += 30;
}

void cat::cleanByBoss()
{
	if (happiness >= 90)
	{
		if (cleanliness >= 80) happiness -= 50;
		cleanliness = 100;
	}
	else
	{
		cout << "愉悦度不够，猫懒得理你" << endl << endl;
	}
}

int cat::catchMouse()
{
	srand((int)time(0));           
	if (random(10) <= 1)        //对猫有概率捉鼠的判断
	{
		if (satiety < 50)
		{
			satiety += 40;
			cleanliness -= 30;
			happiness += 5;
		}
		else
		{
			satiety -= 20;
			cleanliness -= 10;
			happiness += 40;
		}
		return 0;
	}
	return 1;
}

void cat::unInterract()
{
	satiety -= 20;
	cleanliness -= 5;
}

void die()
{
	cout << "对于死亡这个话题我们一直是缺席的，从小我们只学到了要热爱生命、珍惜生命，却从来没有人教过我们如何面对死亡......" << endl << endl

		<< "而我们每一个养宠人都会更加刻意逃避这一天的到来......" << endl << endl

		<< "”到饭点，倒完粮才意识到它已经不在了……“" << endl << endl

		<< "”需要等 5 分钟才敢进家门。我得告诉自己，不会再有人迎接你了……“" << endl << endl

		<< "”床终于变得宽敞了，似乎也变凉了......" << endl << endl

		<< "“由于你的喂食不当你的宠物饿死了..." << endl;
}

int cat::death()
{
	int flag = 1;        //死亡返回flag=0

	if (happiness == 0)  //愉悦度为0，宠物会永远离开你
	{
		cout << "由于你的疏于照顾，小猫一点也不高兴，永远的离开了你" << endl << endl;
		flag = 0;
	}
	else if (sex == "公")
	{
		if (weight < 4 || weight>16)   //公猫死亡时的条件
		{
			die();
			flag = 0;
		}
	}
	else
	{
		if (weight < 2 || weight>10)   //母猫死亡时的条件
		{
			die();
			flag = 0;
		}
	}
	return flag;
}


void cat::change()
{
	int flag = 1;

	if (satiety == 0)
	{
		happiness -= 10;
		weight -= 1;
	}
	else if (satiety == 100) weight += 1;

	if (sex == "公")
	{
		if (weight < 8 || weight>12)
		{
			happiness -= 10;
		}
	}
	else
	{
		if (weight < 4 || weight>8)
		{
			happiness -= 10;
		}
	}

	if (cleanliness == 0)
	{
		happiness -= 30;
	}
	else if(cleanliness>80)
	{
		happiness += 10;
	}

	if (happiness >= 100) happiness = 100;
	if (happiness <= 0) happiness = 0;
	if (satiety >= 100) satiety = 100;
	if (satiety <= 0) satiety = 0;
	if (cleanliness >= 100) cleanliness = 100;
	if (cleanliness <= 0) cleanliness = 0;

}

class dog :public pet
{
public:
	dog(string s = "无", int sa = 0, int ha = 0, int cl = 0, int we = 0) :pet(s, sa, ha, cl, we) {};
	virtual void show();
	virtual void play();
	virtual void shout();
	virtual void change();
	virtual void cleanByBoss();
	virtual void unInterract();
	virtual int death();
};

void dog::show()
{
	cout << "你可爱的小" << getSex() << "狗" << ":" << "属性值如下："
		<< " 饱食度：" << getSatiety() << " 愉悦度：" << getHappiness()
		<< " 清洁度：" << getCleanliness() << " 体重：" << getWeight() << endl << endl;
}

void dog::play()
{
	if (happiness >= 30)
	{
		satiety -= 40;
		happiness += 70;
		cleanliness -= 10;
	}
	else
	{
		cout << "愉悦度达不到要求，狗子懒得理你" << endl << endl;
	}
}

void dog::shout()
{
	cout << "汪汪汪~~  汪汪~  汪汪~ " << endl << endl;
}

void dog::cleanByBoss()
{
	if (happiness >= 70)
	{
		cleanliness = 100;
	}
	else
	{
		cout << "愉悦度不够，狗子懒得洗" << endl << endl;
	}
}

void dog::unInterract()
{
	satiety -= 20;
	happiness -= 20;
	cleanliness -= 20;
}

void dog::change()
{
	if (satiety == 0)
	{
		happiness -= 10;
		weight -= 2;
	}
	else if (satiety == 100) weight += 2;

	if (cleanliness == 0)
	{
		happiness -= 30;
	}
	else if (cleanliness > 80)
	{
		happiness += 10;
	}

	if (weight < 30 || weight>60)
	{
		happiness -= 10;
	}

	if (happiness >= 100) happiness = 100;
	if (happiness <= 0) happiness = 0;
	if (satiety >= 100) satiety = 100;
	if (satiety <= 0) satiety = 0;
	if (cleanliness >= 100) cleanliness = 100;
	if (cleanliness <= 0) cleanliness = 0;
} 

int dog::death()
{
	int flag = 1;
	if (happiness == 0)
	{
		flag = 0;
		cout << "由于你的疏于照顾，狗子一点也不高兴，永远的离开了你" << endl << endl;
	}
	else
	{
		if (weight < 15 || weight>75)
		{
			die();
			flag = 0;
		}
	}
	return flag;
}



void info(int sec)         //界面显示函数
{
	if (!sec) cout << "猫猫去捉鼠了，不能和它互动了哦！" << endl << endl;
	cout << "选择你的行动"<< endl << endl
		<< "1.家教，消耗2个时间，获取50金钱，消耗30体力" << endl << endl
		<< "2.麦当劳兼职，消耗个4时间，获取120金钱，消耗70体力" << endl << endl
		<< "3.割草，消耗1个时间，获取20金钱，消耗20体力" << endl << endl
		<< "4.购买宠物粮食，玩家消耗1个时间，20体力，根据具体宠物粮食消耗金钱。" << endl << endl
		<< "5.休息，玩家消耗1个时间，恢复50体力。" << endl << endl;
	if (sec)
	{
		cout << "6.喂食：玩家消耗1个时间，20体力" << endl << endl
			<< "7.和宠物玩耍：玩家消耗1个时间，50体力。(需愉悦度>=30)" << endl << endl
			<< "8.清洗宠物：玩家消耗1个时间，30体力。(猫猫愉悦度需>=90才可以清洗，狗需>=70)" << endl << endl;
	}
	cout << "9.宠物系统说明。" << endl << endl;
	cout << "10.退出游戏并存档。" << endl << endl;
	cout << "请选择你的行动序号"<<endl << endl;

}

void infomation()        //宠物收养指导书
{
	system("cls");
	cout << "饱食度：宠物的饱食度为0时，会降低10点愉悦度，猫会降低1斤体重，狗会降低2斤体重。" << endl<<endl;
		cout << "宠物饱食度为100时，猫会提高1斤体重，狗会提高2斤体重。宠物被喂食会根据投喂的食物提高" << endl << endl;
		cout << "一定饱食度。宠物玩耍后会根据玩耍和宠物自身情况降低饱食度。" << endl << endl;
		cout << "愉悦度：愉悦度影响宠物对玩家的态度，愉悦度为0时，宠物会离开主人；愉悦度低于30时，" << endl << endl;
		cout << "宠物不会和主人玩耍；愉悦度低于70时，宠物狗不会让主人清洗；宠物猫的愉悦度必须90以上，才会让主人清洗。" << endl << endl;
		cout << "体重：体重是衡量宠物的健康，公猫健康体重为8~12斤，初始时公猫为10斤，母猫健康体重为4~8斤，初始时母猫" << endl << endl;
		cout << "为6斤。公猫体重低于4斤，高于16斤将会因为健康不佳死亡，母猫体重低于2斤，高于10斤将会因为健康死亡。狗健康" << endl << endl;
		cout << "体重为30~60斤，初始时狗会有45斤体重。低于15斤，高于75斤，狗会因为健康死亡。宠物低于超出健康体重时，每个时" << endl << endl;
		cout << "间段都会降低10点愉悦度。" << endl << endl;
		cout << "清洁度：清洁度为0时，宠物愉悦度每个时间段降低30，清洁度高于80时，宠物愉悦度每个时间段升高10。" << endl << endl;
		cout << "宠物自动行为：" << endl << endl;
		cout << "猫的自洁：猫有30% 的可能性进行自洁，消耗1个时间，提高30清洁度；" << endl << endl;
		cout << "猫的随机抓老鼠：在任何时间段，猫有20% 的可能会去抓老鼠，此时主人是" << endl << endl;
		cout << "无法对猫进行交互的。消耗1个时间，如果此时猫的饱食度低于50，会吃掉老鼠" << endl << endl;
		cout << ",提高40饱食度，降低30清洁度，提高5愉悦度。如果此时猫的饱食度大于等于50" << endl << endl;
		cout << "，猫只会玩耍老鼠，降低20饱食度，降低10清洁度，提高40愉悦度。" << endl << endl;
		cout << "非主人交互时间：该时间段一般为主人买东西、打工或休息等无暇顾及宠物的时间段，" << endl << endl;
		cout << "该时间段内宠物将降低20饱食度，另外，狗降低20点愉悦度，和20点清洁度。" << endl << endl;
		cout << "猫不会降低愉悦度，但是会降低5清洁度。" << endl << endl;
		cout << "每天结束时，宠物会强制进入休息，提高30愉悦度，降低5清洁度，降低60饱食度。" << endl << endl;
}

void interactCat(cat& pe, player& pl,int day)
{
	int flag = pe.catchMouse();        //判断猫是否已去捉鼠
	info(flag);
	int sec;
	cin >> sec;
	if (flag)       
	{
		switch (sec)
		{
		case 1:
			if (pl.teach())            //若满足家教的体力和时间条件，下同
			{
				pe.change();           //每过一个时间段宠物状态会变化，家教耗费两个时间段，change两次，下同
				if (pe.catchMouse())  pe.cleanMyself();     //若猫已去捉鼠则不能自洁，下同
				pe.unInterract();
				pe.change();
				if (pe.catchMouse())  pe.cleanMyself();
				pe.unInterract();
			}
			break;
		case 2:
			if (pl.kfc())
			{
				pe.change();
				if (pe.catchMouse())  pe.cleanMyself();
				pe.unInterract();
				pe.change();
				if (pe.catchMouse())  pe.cleanMyself();
				pe.unInterract();
				pe.change();
				if (pe.catchMouse())  pe.cleanMyself();
				pe.unInterract();
				pe.change();
				if (pe.catchMouse())  pe.cleanMyself();
				pe.unInterract();
			}
			break;
		case 3:
			if (pl.cutGrass())
			{
				pe.change();
				if (pe.catchMouse())  pe.cleanMyself();
				pe.unInterract();
			}
			break;
		case 4:
			if (pl.cutGrass())
			{
				pe.change();
				if (pe.catchMouse())  pe.cleanMyself();
				pe.unInterract();
				pl.buyFood();
			}
			break;
		case 6:
			pe.shout();
			pe.change();
			pe.eat(pl.feed());
			break;
		case 5:
			pl.relax();
			pe.change();
			if (pe.catchMouse())  pe.cleanMyself();
			pe.unInterract();
			break;
		case 7:
			pe.change();
			if (pl.playWithPet())
			{
				pe.change();
				pe.play();
			}
			break;
		case 8:
			if (pl.cleanPet())
			{
				pe.change();
			pe.cleanByBoss();
			}
			break;
		case 9:
			infomation();
			break;
		case 10:
			datas da;                            //存档的数据读出
			da.cleanliness = pe.getCleanliness();
			da.day = day;
			da.foods = pl.getFoods();
			da.happiness = pe.getHappiness();
			da.money = pl.getMoney();
			da.satiety = pe.getSatiety();
			da.sex = pe.getSex();
			da.sort = "cat";
			da.strength = pl.getStrength();
			da.time = pl.getTime();
			da.weight = pe.getWeight();
			putData("data", da);                  //存档读入文件
			exit(0);                              //离开游戏
			break;
		}
		

	}
	else
	{
		switch (sec)
		{
		case 1:
			if (pl.teach())
			{
				pe.change();
				pe.unInterract();
				if (pe.catchMouse())  pe.cleanMyself();
				pe.unInterract();
				pe.change();
			}
			break;
		case 2:
			if (pl.kfc())
			{
				pe.change();
				if (pe.catchMouse())  pe.cleanMyself();
				pe.unInterract();
				pe.change();
				if (pe.catchMouse())  pe.cleanMyself();
				pe.unInterract();
				pe.change();
				if (pe.catchMouse())  pe.cleanMyself();
				pe.unInterract();
				pe.change();
			}
			break;
		case 3:
			if (pl.cutGrass())
			{
				pe.change();
				pe.unInterract();
			}
			break;
		case 4:
			if (pl.buyFood())
			{
				pe.change();
				pe.unInterract();
			}
			break;
		case 5:
			pl.relax();
			pe.change();
			pe.unInterract();
			break;
		case 9:
			infomation();
			break;
		case 10:
			datas da;
			da.cleanliness = pe.getCleanliness();
			da.day = day;
			da.foods = pl.getFoods();
			da.happiness = pe.getHappiness();
			da.money = pl.getMoney();
			da.satiety = pe.getSatiety();
			da.sex = pe.getSex();
			da.sort = "cat";
			da.strength = pl.getStrength();
			da.time = pl.getTime();
			da.weight = pe.getWeight();
			putData("data", da);
			exit(0);
			break;
		}
	}
}

void interactdog(dog& pe, player& pl,int day)
{
	info(1);
	int sec;
	cin >> sec;
	switch (sec)
	{
	case 1:
		if (pl.teach())
		{
			pe.change();
			pe.unInterract();
			pe.change();
			pe.unInterract();
		}

		break;
	case 2:
		if (pl.kfc())
		{
			pe.change();
			pe.unInterract();
			pe.change();
			pe.unInterract();
			pe.change();
			pe.unInterract();
			pe.change();
			pe.unInterract();
		}
		break;
	case 3:
		if (pl.cutGrass())
		{
			pe.change();
			pe.unInterract();
		}
		break;
	case 4:
		if (pl.buyFood())
		{
			pe.change();
			pe.unInterract();
		}
		break;
	case 6:
		pe.shout();
		pe.change();
		pe.eat(pl.feed());
		break;
	case 5:
		pl.relax();
		pe.change();
		pe.unInterract();
		break;
	case 7:
		if (pl.playWithPet())
		{
			pe.change();
			pe.play();
		}
		break;
	case 8:
		if (pl.cleanPet())
		{
			pe.change();
			pe.cleanByBoss();
		}
		break;
	case 9:
		infomation();
		break;
	case 10:
		datas da;
		da.cleanliness = pe.getCleanliness();
		da.day = day;
		da.foods = pl.getFoods();
		da.happiness = pe.getHappiness();
		da.money = pl.getMoney();
		da.satiety = pe.getSatiety();
		da.sex = pe.getSex();
		da.sort = "cat";
		da.strength = pl.getStrength();
		da.time = pl.getTime();
		da.weight = pe.getWeight();
		putData("data", da);
		exit(0);
		break;
	}
}


void adopt()
{
	cout << "请选择你想养的宠物 (1)猫 or (2)狗" << endl;
	int sec;
	cin >> sec;
	player me;
	string sex;
	int secp;
	int a=80, b=80, c=80, d;          //给宠物初始的属性值
	if (sec == 1)
	{
		cout << "请好好对待这只小猫哦~" << endl << endl;
		cout << "你是想养只公猫猫还是只母猫猫" << endl << endl;
		cout << "(1) 公猫猫  (2) 母猫猫 " << endl << endl;
		int sec2;
		cin >> sec2;
		if (sec2 == 1)                //根据性别初始属性值
		{
			sex = "公";
			d = 10;
		}
		else
		{
			sex = "母";
			d = 6;
		}
	}
	else
	{
		cout << "你是想养只公狗子还是只母狗子" << endl << endl;
		cout << "(1) 公狗子  (2) 母狗子 " << endl << endl;
		int sec2;
		cin >> sec2;
		if (sec2 == 1)
		{
			sex = "公";
			d = 45;
		}
		else
		{
			sex = "母";
			d = 45;
		}
		cout << "请好好对待这只小狗哦~" << endl << endl;
		secp = 1;
	}
	cat pecat(sex, a, b, c, d);
	dog pedog(sex, a, b, c, d);

	int day = 0;
	string temp;
	while (day != 30)      //当玩完30天游戏圆满结束
	{
		if (sec==1)        //猫狗的判断
		{
			int life = 1;
			system("cls");  //清屏
			while (me.getTime()>0)     //当今天时间为0时进入下一天
			{
				system("cls");
				cout << "今天是与萌宠相伴的第" << day + 1 << "天" << endl << endl;
				pecat.balance();       //活动开始前把溢出的属性值调为上下限
				me.change();
				me.show();             //每一次活动前，显示当前任务和宠物的属性
				pecat.show();
				interactCat(pecat, me,day);
				if (!pecat.death())     //死亡时退出循环游戏结束
				{
					life = 0;
					break;
				}
				cout << "任意输入按回车进入下一时间段" << endl << endl;
				cin >> temp;
			}
			if (!life) break;
			day++;                       
			me.sleep();                 //每过一天会睡眠一次
			pecat.dayEnd();             //宠物每过一天的状态改变
		}
		else
		{
			int life = 1;
			system("cls");
			cout << "第" << day + 1 << "天开始了" << endl << endl;
			while (me.getTime() > 0)
			{
				system("cls");
				cout << "今天是与萌宠相伴的第" << day + 1 << "天" << endl << endl;
				pedog.balance();
				me.change();
				me.show();
				pedog.show();
				interactdog(pedog, me,day);
				if (!pedog.death())
				{
					life = 0;
					break;
				}
				cout << "任意输入按回车进入下一时间段" << endl << endl;
				cin >> temp;
			}
			if (!life) break;
			day++;
			me.sleep();
			pedog.dayEnd();
		}
	}
	if (day == 30) cout << "完结撒花，宠物寿终正寝！" << endl << endl;
}


void continueAdopt(datas da)
{
	player me(da.strength, da.money, da.time);
	me.foodGet(da.foods);
	if (da.sort == "cat")
	{
		cat pecat(da.sex, da.satiety, da.happiness, da.cleanliness, da.weight);
		int day = da.day;
		string temp;
		while (day != 30)
		{
			if (typeid(cat) == typeid(pecat))
			{
				int life = 1;
				system("cls");
				while (me.getTime() > 0)
				{
					system("cls");
					cout << "今天是与萌宠相伴的第" << day + 1 << "天" << endl << endl;
					pecat.balance();
					me.change();
					me.show();
					pecat.show();
					interactCat(pecat, me,day);
					if (!pecat.death())
					{
						life = 0;
						break;
					}
					cout << "任意输入按回车进入下一时间段" << endl << endl;
					cin >> temp;
				}
				if (!life) break;
				day++;
				me.sleep();
				pecat.dayEnd();
			}
		}
		if (day == 30) cout << "完结撒花，宠物寿终正寝！" << endl << endl;
	}
	if (da.sort == "dog")
	{
		dog pedog(da.sex, da.satiety, da.happiness, da.cleanliness, da.weight);
		int day = da.day;
		string temp;
		while (day != 30)
		{
			if (typeid(dog) == typeid(pedog))
			{
				int life = 1;
				system("cls");
				while (me.getTime() > 0)
				{
					system("cls");
					cout << "今天是与萌宠相伴的第" << day + 1 << "天" << endl << endl;
					pedog.balance();
					me.change();
					me.show();
					pedog.show();
					interactdog(pedog, me,day);
					if (!pedog.death())
					{
						life = 0;
						break;
					}
					cout << "任意输入按回车进入下一时间段" << endl << endl;
					cin >> temp;
				}
				if (!life) break;
				day++;
				me.sleep();
				pedog.dayEnd();
			}
		}
		if (day == 30) cout << "完结撒花，宠物寿终正寝！" << endl << endl;
	}
}


void getData(const string& filename, datas& data)
{
	ifstream fin(filename);
	if (fin.good())
	{
		fin>>data.day>>data.sort>>data.strength>>data.money>>data.time>>
		data.sex>>data.satiety>>data.happiness>>data.cleanliness>>data.weight;
		string str; int num;
		while (fin >> str >> num)     //食物的读入
		{
			data.foods[str] = num;
		}
	}
	fin.close();
}

void putData(const string& filename,datas data)
{
	ofstream fout(filename);
	if (fout.good())
	{
		fout<<data.day<<"	"<<data.sort<<"	"<<  data.strength <<"	"<< data.money <<"	"<< data.time <<"	"<<
			data.sex <<"	"<< data.satiety <<"	"<< data.happiness <<"	"<< data.cleanliness <<"	"<< data.weight;
		string str; int num;
		for(map<string,int>::iterator i=data.foods.begin();i!=data.foods.end();i++)   //食物的存入
		{
			fout << i->first;
			fout << "	" << i->second;
		}
	}
	fout.close();
}


int main()
{
	cout <<"欢迎来到电子宠物养成系统~" << endl<<endl;
	cout << "选择（1）开始游戏或（2）读取存档"<<endl<<endl;
	cout << "请输入选择：" << endl;
	int sec;
	cin >> sec;
	if (sec == 1)
	{
		adopt();        //开始新的游戏
	}
	else
	{
		datas da;
		getData("data", da);       //取出文档数据
		continueAdopt(da);        //读取存档继续游戏
	}
}

```

