//
//  LGSocketServer.h
//  hupai
//
//  Created by wangyilu on 16/5/31.
//  Copyright © 2016年 ___PURANG___. All rights reserved.
//

//自己设定
//#define HOST @"192.168.2.85"
//#define PORT 8080

//设置连接超时
#define TIME_OUT 20

enum{
    SocketOfflineByServer,// 服务器掉线，默认为0
    SocketOfflineByUser,  // 用户主动cut
    SocketOfflineByWifiCut,
};

#import <Foundation/Foundation.h>
#import "AsyncSocket.h"

@interface LGSocketServer : NSObject<AsyncSocketDelegate>

@property (nonatomic, strong) AsyncSocket         *socket;       // socket

@property (nonatomic, retain) NSTimer             *heartTimer;   // 心跳计时器

@property (nonatomic, strong) NSString         *host;

@property (nonatomic, assign) NSInteger port;

+ (NSString *)getIPAddress:(BOOL)preferIPv4;
+ (BOOL)isValidatIP:(NSString *)ipAddress;
+ (NSDictionary *)getIPAddresses;

+ (LGSocketServer *)sharedSocketServe;

//  socket连接
- (void)startConnectSocket;

// 断开socket连接
-(void)cutOffSocket;

// 发送消息
- (void)sendMessage:(id)message type:(int)type;

@end
