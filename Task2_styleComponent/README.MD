# Styled-Components
## Styled-Components:
 Là một thư viện giúp bạn có thể tổ chức và quản lý code CSS một cách dễ dàng trong các project React. Nó được xây dựng với mục tiêu giữ cho các styles của các components trong React gắn liền với chính các components đó. Nó cung cấp một interface rõ ràng và dễ sử dụng cho cả React và React Native.
## Ưu điểm và nhươc điểm của Style Components:
 ### Ưu điểm:
+ Quản lý CSS hiệu quả: Style Components cho phép bạn quản lý CSS bằng JavaScript, giúp tạo và quản lý styles dễ dàng, đặc biệt trong các ứng dụng React lớn.

+ Component-Based Styling: Style Components thúc đẩy việc tạo các styles cho từng thành phần (component) riêng lẻ, giúp tránh xung đột styles và tạo components độc lập.

+ Dynamic Styles: Bạn có thể dễ dàng tạo styles dựa trên props của component, cho phép tạo các styles động và linh hoạt.

+ Server-Side Rendering (SSR): Style Components hỗ trợ Server-Side Rendering, giúp tối ưu hóa hiệu suất và SEO của ứng dụng.

+ Theming: Bạn có thể tạo chủ đề (themes) dễ dàng và thay đổi giao diện của ứng dụng một cách linh hoạt.

+ Scoped Styles: Styles trong Style Components được áp dụng cục bộ, tránh xung đột và tạo ra môi trường phát triển an toàn.

+ Hạn chế CSS Specificity: Style Components giúp giảm thiểu việc sử dụng các lựa chọn CSS phức tạp, giúp tránh xung đột styles.
### Nhược điểm: 
+ Học cách mới: Đối với những người mới học hoặc làm quen với Style Components, có thể cần thời gian để học cách sử dụng và hiểu cách làm việc với CSS trong JavaScript.

+ Tính trực quan thấp: So với các công cụ trực quan, như các trình soạn thảo CSS, việc viết styles bằng JavaScript có thể trở nên ít trực quan hơn đối với một số người.

+ Khó tự động hóa: Việc tự động hóa một số quy trình liên quan đến styles (ví dụ: tạo sprite sheets cho ảnh) có thể khó hơn so với việc sử dụng CSS truyền thống.

+ Không phù hợp cho mọi dự án: Style Components có thể không phù hợp cho mọi loại dự án. Đối với các ứng dụng nhỏ hoặc đơn giản, việc sử dụng CSS truyền thống có thể đủ.
## Cách cài đặt và sử dụng styled-comments:
- Cài đặt trên môi trường npm or yarn ta sử dụng một trong 2 câu lệnh sau: 
```
# with npm
npm install styled-components

# with yarn
yarn add styled-components

```
- Để sử dụng nó ở các file mà chúng ta cần sử dụng thì sử dụng câu lệnh sau để import.
```
 import styled from 'styled-components';
```
- Về cơ bản styled-components là một dạng viết CSS trực tiếp trong file tsx <==> như tsx viết html trong ts
	CSS-in-TS
	
- Cài extensiton : styled-components-snippets ==> dùng cho tiện tren vscode scp,
## Tổng hợp cách sử dụng styled-components:
1. ### Sử dụng hàm styled để tạo một component style mới:
```
// Tạo thành phần Tiêu đề sẽ hiển thị thẻ <h1> với một số kiểu
const Title = styled.h1`
  font-size: 1.5em;
  text-align: center;
  color: #BF4F74;
`;

// Tạo thành phần Wrapper sẽ hiển thị thẻ <section> với một số kiểu
const Wrapper = styled.section`
  padding: 4em;
  background: papayawhip;
`;

//Sử dụng Tiêu đề và Trình bao bọc giống như bất kỳ thành phần React nào khác – ngoại trừ việc chúng được tạo kiểu!
render(
  <Wrapper>
    <Title>
      Hello World!
    </Title>
  </Wrapper>
);
```
2. ### Sử dụng Template Literals kết hợp với Props:
```
import styled from 'styled-components';

const Button = styled.button`
  background-color: ${(props) => (props.primary ? 'blue' : 'white')};
  color: ${(props) => (props.primary ? 'white' : 'black')};
  padding: 10px 20px;
  border: 1px solid ${(props) => (props.primary ? 'blue' : 'black')};
  cursor: pointer;
  font-size: 16px;

  &:hover {
    background-color: ${(props) => (props.primary ? 'darkblue' : 'lightgray')};
  }
`;

const App = () => {
  return (
    <div>
      <Button primary>Primary Button</Button>
      <Button>Secondary Button</Button>
    </div>
  );
};

```
3. ### Extending Styles
- Để dễ dàng tạo một thành phần mới kế thừa kiểu dáng của thành phần khác, chỉ cần bọc nó trong styled() hàm tạo.Sử dụng nút từ phần trước và tạo một nút đặc biệt, mở rộng nó với một số kiểu dáng liên quan đến màu sắc:
```
// Nút từ phần cuối cùng không có nội suy
const Button = styled.button`
  color: #BF4F74;
  font-size: 1em;
  margin: 1em;
  padding: 0.25em 1em;
  border: 2px solid #BF4F74;
  border-radius: 3px;
`;

// Một thành phần mới dựa trên Nút nhưng có một số kiểu ghi đè
const TomatoButton = styled(Button)`
  color: tomato;
  border-color: tomato;
`;

render(
  <div>
    <Button>Normal Button</Button>
    <TomatoButton>Tomato Button</TomatoButton>
  </div>
);

```
4. ### Thư viện Theme:
- Nếu bạn sử dụng themes, bạn có thể truyền theme vào component style thông qua ThemeProvider. Sau đó, bạn có thể sử dụng theme để áp dụng màu sắc hoặc giá trị khác vào styles.
```
import {ThemeProbider} from "styled-components";
			const Button = styled.button`
			  font-size: 1em;
			  margin: 1em;
			  padding: 0.25em 1em;
			  border-radius: 3px;

			  /* them màu qua props theme.main */
			  color: ${props => props.theme.main};
			  border: 2px solid ${props => props.theme.main};
			`;

			// Tạo một object có chứa mảng thông tin màu 
			const theme = {
			  main: "mediumseagreen"
			};

			render(
			  <div>
				<Button theme={{ main: "royalblue" }}>Ad hoc theme</Button>
				<ThemeProvider theme={theme}>
				  <div>
					<Button>Themed</Button>
					<Button theme={{ main: "darkorange" }}>Overridden</Button>
				  </div>
				</ThemeProvider>
			  </div>
			);

	* chú ý mảng này để thưc hiện nâng cao hơn
	import { withTheme } from 'styled-components'
	import { useContext } from 'react'
	import { ThemeContext } from 'styled-components'	
	import { useTheme } from 'styled-components'

```
5. ### Global styled 
```
*dùng để tạo một số CSS chung cho dự án 
	 vd1 :
		import { createGlobalStyle } from "styled-components";
		import { GlobalClass } from "./..."
		export const GlobalStyle = createGlobalStyle`
		@import url('....') // url font chữ tải trên google font 
		body {
			font-family: 'Poppins', sans-serif;
			};
		${GlobalClass} // đưa được file class vào trung trong file global
		`;
		
	*ngoài ra có thể tạo thêm một file GlobalClass để đưa thêm một số class dùng trung ở global vào 
			
		import {css} from "styled-components";
		
		export const GlobalClasses = css`
		.demo{
			display: flex;
			justify-content: space-between;
			align-items: center;
		}

		`;

```
6. ### Animations
```
// Create the keyframes
const rotate = keyframes`
  from {
    transform: rotate(0deg);
  }

  to {
    transform: rotate(360deg);
  }
`;

// Here we create a component that will rotate everything we pass in over two seconds
const Rotate = styled.div`
  display: inline-block;
  animation: ${rotate} 2s linear infinite;
  padding: 2rem 1rem;
  font-size: 1.2rem;
`;

render(
  <Rotate>&lt; 💅🏾 &gt;</Rotate>
);

```
7. ### Attaching additional props
```
const Input = styled.input.attrs<{ $size?: string }>((props) => ({
	type: 'text',
	$size: props.$size || '1em',
}))`
	border: 2px solid #bf4f74;
	margin: ${(props) => props.$size};
	padding: ${(props) => props.$size};
`;

// Input's attrs will be applied first, and then this attrs obj
const PasswordInput = styled(Input).attrs({
  type: "password",
})`
  // similarly, border will override Input's border
  border: 2px solid aqua;
`;

render(
  <div>
    <Input placeholder="A bigger text input" $size="2em" />
    <br />
    {/* Notice we can still use the size attr from Input */}
    <PasswordInput placeholder="A bigger password input" $size="2em" />
  </div>
);
```
### Tổng kết 
 1. sử dụng styled-components dạng CSS in ts, ngoài ra cấu trúc có thể viết như SCSS
2. chú ý cách dùng theme, props, css,.attrs, components
3. cách dùng createGlobalStyle,Tagged Template Literals,Animations