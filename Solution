  #include <iostream>

using namespace std;
int game1[3][3];
int game2[7][7];
int game3[10][10];
int row = 0;
int col = 0;



void init(int);
void randOutput();
void makeMoveGameOne();
void gameOnePlayerOne();
void gameOnePlayerTwo();
void gameTwoPlayerOne();
void gameTwoPlayerTwo();
void gameThreePlayerOne();
void gameThreePlayerTwo();


int main()
{
    int N,K;
    cin>>N>>K;

    init(N);

    if(N==3){
        if(K==1){
            gameOnePlayerOne(); }
        else gameOnePlayerTwo(); }
    if(N==7){
        if(K==1){
            gameTwoPlayerOne();}
        else gameTwoPlayerTwo();}
    if(N==10){
        if(K==1) {
            gameThreePlayerOne();}
        else gameThreePlayerTwo();}

    cout<<row<<" "<<col;

    return 0;
}

void init(int n)
{
    if(n==3)
    {
        for(int i=0;i<3;i++)
            for(int j=0;j<3;j++)
                cin>>game1[i][j];

    }
    else if(n==7)
    {
        for(int i=0;i<7;i++)
            for(int j=0;j<7;j++)
                cin>>game2[i][j];

    }
    else
    {
        for(int i=0;i<10;i++)
            for(int j=0;j<10;j++)
                cin>>game3[i][j];
    }



}

void gameOnePlayerOne()
{
    for(int i=0;i<2;i++)
        for(int j=0;j<2;j++)
            if(game1[i][j]==0)
            {
                row=1;
                col=1;
            }


    if(game1[1][1]==1 && game1[1][0]!=1 && game1[0][0] !=1)
    {
        if(game1[1][0]==0)
        {
            row=1;
            col=0;
        }

        else if(game1[0][0]==0)
        {
            row=0;
            col=0;
        }

    }
    else if(game1[1][1]==1 && game1[1][2]!=1 && game1[2][2] !=1)
    {
        if(game1[1][2]==0)
            {
                row=1;
                col=2;
            }
        else if(game1[2][2]==0)
        {
            row=2;
            col=2;
        }

    }
}


void gameOnePlayerTwo()
{
    if(game1[1][1]==1)
    {
        randOutput();
    }
    else if(game1[1][1]==0)
    {
        row=1;
        col=1;
    }
    else{
        makeMoveGameOne();
    }



    }




void gameTwoPlayerOne()
{
    bool first=true;
    for(int i=0;i<7;i++)
    for(int j=0;j<7;j++)
        if(game2[i][j]!=0)
        {
            first=false;
        }
    int rowMax=0;
    int colMax=0;
    if(first)
    {
        row=0;
        col=0;
    }else
    {




        for(int i=0;i<7;i++){
            for(int j=0;j<7;j++)
            {
                if(game2[i][j]==1 &&  (i>=rowMax || j>=colMax ) )
                {
                    rowMax=i;
                    colMax=j;
                }
            }
        }
        if(game2[rowMax][colMax+1]==0 && game2[rowMax][6]==0)
        {
            row=rowMax;
            col=colMax+1;
        }else if(game2[rowMax+1][colMax+1]==0)
        {
            row=rowMax+1;
            col=colMax+1;
        }
        else{
            row=rowMax;
            col=colMax-1;
        }

    }


}

bool path2(int,int);
bool warpath2(int,int);
bool bounds2(int x, int y)
            {
              return  x>=0 && y<=6 &&  x>=0 && y<=6;
            }
void gameTwoPlayerTwo()
{
    bool move=false;
    bool countermove=false;
    int rowInd=-1;
    int colInd=-1;
    for(int i=0;i<7;i++)
    {
        for(int j=0;j<7;j++)
        {
            if(game2[i][j]==0)
            {

                game2[i][j]==2;
                if(path2(i,j))
                {
                    move= true;
                    rowInd=i;
                    colInd=j;
                }else{
                    game2[i][j]==0;
                }
            }
        }
    }
    if(move)
    {
        row=rowInd;
        col=colInd;
    }else
    {
        for(int i=0;i<7;i++)
        {
            for(int j=0;j<7;j++)
            {

                if(game2[i][j]==0)
                {
                    game2[i][j]==1;
                    if(warpath2(i,j))
                    {
                        countermove= true;
                        rowInd=i;
                        colInd=j;
                    }else{
                        game2[i][j]==0;
                    }
                }
            }
        }

        if(countermove)
        {
            row=rowInd;
            col=colInd;
        }else{
            bool target=false;
            bool latch=false;

            for(int i=0;i<7;i++)
            {
                for(int j=0;j<7;j++)
                {
                    if(game2[i][j]==1)
                    {
                        target=true;

                    }
                    if(target)
                    {
                        if(game2[i][j+1]==0 && bounds2(i,j+1))
                        {
                            row =i;
                            col =j+1;
                            return;
                        }else if   ( game2[i+1][j+1]==0 && bounds2(i+1,j+1) )
                        {
                            row=i+1;
                            col=j+1;
                            return;
                        }else if(game2[i-1][j]==0 && bounds2 (i-1,j))
                        {
                            row=i-1;
                            col=j;
                            return;
                        }else {

                            for(int i=0;i<7;i++)
                                for(int j=0;j<7;j++)
                            {
                                if(game2[j][i]==0)
                                {
                                    row=j;
                                    col=i;
                                    return;
                                }
                            }
                        }
                    }
                }
            }


        }
    }

}
bool path2(int x,int y)
{
    if( game2[x][y]==1 || game2[x][y]==0) return false;
    else if(path2(x+1,y) && path2[x+1][y+1] &&path2[x-1][y-1] && path2[x-1][y] )
        return false;
    return true;
}
bool warpath2(int x,int y)
{
    if( game2[x][y]==2 || game2[x][y]==0) return false;
    else if(path2(x,y+1) && path2[x+1][y+1] &&path2[x-1][y-1] && path2[x][y-1] )
        return false;
    return true;
}




void gameThreePlayerOne()
{
    bool first=true;
    for(int i=0;i<10;i++)
    for(int j=0;j<10;j++)
        if(game3[i][j]!=0)
        {
            first=false;
        }
    int rowMax=0;
    int colMax=0;
    if(first)
    {
        row=0;
        col=0;
    }else
    {




        for(int i=0;i<10;i++){
            for(int j=0;j<10;j++)
            {
                if(game3[i][j]==1 &&  (i>=rowMax || j>=colMax ) )
                {
                    rowMax=i;
                    colMax=j;
                }
            }
        }
        if(game3[rowMax][colMax+1]==0 && game3[rowMax][9]==0)
        {
            row=rowMax;
            col=colMax+1;
        }else if(game3[rowMax+1][colMax+1]==0)
        {
            row=rowMax+1;
            col=colMax+1;
        }
        else{
            row=rowMax;
            col=colMax-1;
        }

    }

}

bool path3(int,int);
bool warpath3(int,int);
bool bounds3(int x, int y)
            {
              return  x>=0 && y<=9 &&  x>=0 && y<=9;
            }
void gameThreePlayerTwo()
{
    bool move=false;
    bool countermove=false;
    int rowInd=-1;
    int colInd=-1;
    for(int i=0;i<10;i++)
    {
        for(int j=0;j<10;j++)
        {
            if(game3[i][j]==0)
            {

                game3[i][j]==2;
                if(path3(i,j))
                {
                    move= true;
                    rowInd=i;
                    colInd=j;
                }else{
                    game3[i][j]==0;
                }
            }
        }
    }
    if(move)
    {
        row=rowInd;
        col=colInd;
    }else
    {
        for(int i=0;i<10;i++)
        {
            for(int j=0;j<10;j++)
            {

                if(game3[i][j]==0)
                {
                    game3[i][j]==1;
                    if(warpath3(i,j))
                    {
                        countermove= true;
                        rowInd=i;
                        colInd=j;
                    }else{
                        game3[i][j]==0;
                    }
                }
            }
        }

        if(countermove)
        {
            row=rowInd;
            col=colInd;
        }else{
            bool target=false;
            bool latch=false;

            for(int i=0;i<10;i++)
            {
                for(int j=0;j<10;j++)
                {
                    if(game3[i][j]==1)
                    {
                        target=true;

                    }
                    if(target)
                    {
                        if(game3[i][j+1]==0 && bounds3(i,j+1))
                        {
                            row =i;
                            col =j+1;
                            return;
                        }else if   ( game3[i+1][j+1]==0 && bounds3(i+1,j+1) )
                        {
                            row=i+1;
                            col=j+1;
                            return;
                        }else if(game3[i-1][j]==0 && bounds3 (i-1,j))
                        {
                            row=i-1;
                            col=j;
                            return;
                        }else {

                            for(int i=0;i<10;i++)
                                for(int j=0;j<10;j++)
                            {
                                if(game3[j][i]==0)
                                {
                                    row=j;
                                    col=i;
                                    return;
                                }
                            }
                        }
                    }
                }
            }


        }
    }


}
bool path3(int x,int y)
{
    if( game3[x][y]==1 || game3[x][y]==0) return false;
    else if(path3(x+1,y) && path3[x+1][y+1] &&path3[x-1][y-1] && path3[x-1][y] )
        return false;
    return true;
}
bool warpath3(int x,int y)
{
    if( game3[x][y]==2 || game3[x][y]==0) return false;
    else if(path3(x,y+1) && path3[x+1][y+1] &&path3[x-1][y-1] && path3[x][y-1] )
        return false;
    return true;
}

void randOutput()
{
    for(int i=0;i<3;i++)
        for(int j=0;j<3;j++)
            if(game1[i][j]==0)
            {
                row=i;
                col=j;
            }
}



void makeMoveGameOne()
{
    if(game1[0][0]==2 || game1[0][1]==2)
    {
        if(game1[2][1]==0)
        {
            row=2;
            col=1;
        }
        if(game1[2][2]==0)
        {
            row=2;
            col=2;
        }
    }else if(game1[2][1]==2 || game1[2][2]==2)
    {
        if(game1[0][1]==0)
        {
            row=0;
            col=1;
        }
        if(game1[0][0]==0)
        {
            row=0;
            col=0;
        }
    }else{
        bool rowDanger=false;
        bool colWin = false;
        int rowSum=0;
        int colSum=0;
        int rowInd=-1;
        int colInd=-1;
        int i=0;
        int j=0;
        while(i<3 && !rowDanger)
        {
            while(j<3)
            {
                if(game1[i][j]==1)
                {
                    rowSum++;
                }
                ++j;
            }
            if(rowSum>=2)
            {
                rowDanger=true;
                rowInd=i;
            }
            ++i;
        }
        if(rowDanger)
        {
            for(int i=0;i<3;i++)
            {
                if(game1[rowInd][i]!=1)
                {
                    colInd=i;
                }
            }
            row=rowInd;
            col=colInd;

        }
    }

}
