# DB Architecture

table festival{
  fid int pk
  name varchar(30)
  place varchar(50)
  lat float
  lng float
  opendate datetime
  type varchar(10)
  content varchar(255)
  hostinfo varchar(50)
  image BLOB
}
TABLE festaimg{
    fid int 
    image BLOB
}
table member{
  mid varchar(20) pk
  pw varchar(20)
  email varchar(30)
  phone varchar(20)
}
table review{
  mid varchar(20)
  content varchar(150)
  fid int
  writedate datetime
  grade int
}
TABLE notice{
 nid int pk
 ncontent varchar(255)
 uploaddate datetime
 writer varchar(20)
 cnt int
}
table myfesta{
    mid varchar(20)
    fid int
}
ref{
  review.fid > festival.fid
}
ref{
  review.mid > member.mid
}
ref{
  myfesta.mid > member.mid
}
ref{
  myfesta.fid > festival.fid
}
ref{ 
  festaimg.fid > festival.fid
}

![festa_db](festa_db.png)